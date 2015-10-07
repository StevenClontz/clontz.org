---
kind: article
title: "Using email addresses for Django usernames"

created_at: 2012-11-15 12:58

---

[Django](https://www.djangoproject.com/) is a great Python framework for database-driven sites. It's what we use for [Teloga](http://www.teloga.com) in fact. But there's one thing that bugs me: usernames are case-sensitive.

With Teloga busy serving both the [Auburn University Bands](http://www.teloga.com/networks/aubands/) and the [Alabama Bandmasters Association](http://www.teloga.com/networks/aba/), it didn't take too long for us to realize that this is very unintuitive for users. We received weekly emails complaining that this person couldn't log into their account, and invariably it'd be caused by the usage of Steven@Teloga.com instead of steven@teloga.com. That had to go.

<!-- more -->

First things first. Before the case-sensitivity even came up, we first decided we wanted to use emails as logins. In addition, we're going to need longer usernames than the 30 characters Django allows out of the box, since email addresses can [be up to 256 characters long](http://email.about.com/od/emailbehindthescenes/f/address_length.htm).

That's where [django-longer-username](https://github.com/GoodCloud/django-longer-username) comes in. It's a really nice plugin which provides a [South](http://south.aeracode.org/) migration for your database and tweaks all the admin forms appropriately.

Once we have a setup for longer usernames (we went with 75 characters as sufficient for our needs), we needed to create our own registration form. [James](http://www.jdabbs.com) took care of this for Teloga. Here's a sketch of what ours looks like:

```
class RegistrationForm(forms.Form):
    email = forms.EmailField(
        max_length=75,  # must be 30 without longerusername
        widget=forms.TextInput(attrs={'class': 'xlarge'}),
        label='Email')
    password = forms.CharField(
        widget=forms.PasswordInput(attrs={'class': 'xlarge'}),
        label='Password')
    password_confirmation = forms.CharField(
        widget=forms.PasswordInput(attrs={'class': 'xlarge'}),
        help_text='Enter the same password as above, for verification.',
        label='Confirm password'
    )
    
    def clean_email(self):
        """ Verifies that this email is not already in use """
        email = self.cleaned_data['email'].lower() # Oh hey, this is important.
        try:
            User.objects.get(email=email)
            raise forms.ValidationError('That email address is already associated with an account.')
        except User.DoesNotExist:
            return email

    def clean_password_confirmation(self):
        """ Verifies that both password fields match """
        data = self.cleaned_data
        pswd = data.get('password', '')
        conf = data.get('password_confirmation', '')
        if pswd and (pswd != conf):
            raise forms.ValidationError("The password confirmation didn't match.")
        return conf

    def register(self):
        """ Creates a new user object. """
        data = self.cleaned_data
        email = data['email']  # We will use the email address as both u.username and u.email
        password = data['password']
        user = User.objects.create_user(email, email=email, password=password)
        return user
```

I'll draw attention to this line:

    email = self.cleaned_data['email'].lower() # Oh hey, this is important.
    
This is getting back to the point I made at first: case sensitivity for usernames sucks. Particularly when you're dealing with emails: while it's up to each email provider to decide if they want their email addresses to be case-sensitive, most of them make the (smart) decision to ignore capitalization. So do yourself a favor and ignore it yourself. (In our case, we didn't at first, and had a few dozen users make duplicate accounts with various capitalizations of their email address.)

Now, using this form you will have users with all-lowercase email addresses set as the username. So now it's time to get them logged in.

We're actually just going to do a short adjustment to the stock AuthenticationForm. We need to make sure that the length of the username field is increased to 75, and we better make sure we clean up the username/email so that it's all lowercase. (Otherwise you're going to get a rightfully perturbed user complaining that they registered with Steven@Teloga.com but they cannot log in, because you stored their email as steven@teloga.com.)

```
from django.contrib.auth.forms import AuthenticationForm as StockAuthenticationForm

class AuthenticationForm(StockAuthenticationForm):
    username = forms.EmailField(max_length=75, label='Email')  # requires longerusername
    # don't forget to make the email lowercase
    def clean_username(self):
        u = self.cleaned_data.get('username')
        return u.lower()
```

So, all in all there isn't anything too fancy here, but I was surprised I couldn't find a walkthrough online so I thought I could whip one up. Let me know if you have any comments!

-SXC