---
layout: page
title: "Online Streaming in Mathematics"
description: "supporting broader distribution of oral presentations"
header-img: "img/osm-bg.jpg"
permalink: /math/osm/
---

## Why OSM?

Cutting-edge research in mathematics happens faster than peer-reviewed
publication. Thankfully, tools like the [arXiv](https://arxiv.org/)
allow us to share initial written reports with colleagues, even
as the results are refined, edited, and refereed.

But another major way we propogate our findings are in oral presenatations.
These talks, given anywhere from university seminars to international meetings,
are an excellent opportunity to inspire others to read our full articles,
ask useful questions, and collaborate on new ideas. Unlike a paper, a talk
gives us the opportunity to encapsulate complex ideas into an intuitive
explanations. 

But attending a talk is much more involved than downloading a PDF. Faculty
and students fortunate to be located physically nearby a seminar or
conference have an extra advantage to attend, as do professors with
funding to support airfare and lodging. We always request our funding
organizations to support young researchers to attend important conferences,
but often the promised amount is insufficient to even cover lodging,
much less airfare.

I think livestreaming more of our oral presentations in mathematics
is part of the solution to this inequity, which is why I've put together
this page to explain how surprisingly easy it is to livestream mathematical 
content 
(you probably have most of the equipment available in your department already), 
and the 
[Online Streaming in Mathematics YouTube Channel](https://www.youtube.com/channel/UCfaU4ITYd-mwolEox3SxvWw)
to host the streams and archives for talks given in my research community.

I want to thank the organizers of the 
[2018 Spring Topology/Dynamics Confernece](http://www.auburn.edu/~kuperkm/STDC2018/)
and its set-theoretic topology special session
for accepting my offer to livestream much of the conference procedings.
While I've been working on this initiative since my last year of graduate
school, much of the content of this page is based on that experience.

## Equipment

By design, I've focused on equipment that is often already available to
faculty whenever possible, as well as a configuration that is easiest to
implement with minimal disruption to usual conference proceedings.

These are the items you'll want to acquire for each *simultaneous* stream
you wish to produce.

- Video Camera
    - Required features:
        - Mountable on tripod (see below)
        - 720p video, decent sound recording using internal microphone
        - HDMI output (including cable)
        - Able to output video through HDMI without recording
          (tip: disable "demo mode")
    - Confirmed models:
        - [SONY HDR-CX200](https://esupport.sony.com/US/p/model-home.pl?mdl=HDRCX200)
- Tripod
    - Required features:
        - Can mount video camera stabily at various heights
        - Allows panning of camera to track speaker movement
    - Confirmed models:
        - [Zeikos tripod](https://www.amazon.com/Zeikos-ZE-TR57A-57-Inch-Carrying-Camcorders/dp/B001J7GPGQ)
- HDMI-USB Converter
    - Required features:
        - Converts HDMI audio/video signal into USB signal for use on computer
        - USB 3.0 cable (available separately)
    - Confirmed models:
        - [Magewell USB Capture HDMI Gen 2](https://www.bhphotovideo.com/c/product/1105735-REG/magewell_xi_100_d_usb_hdmi_one_hd_hdmi_usb.html) 
- Laptop
    - Required features:
        - Windows, Mac, or Linux
        - Sufficient power for running software described below 
          (8GB RAM, 2.6 GHz processor using Windows 10 
          is sufficient, but probably not necessary)
        - USB 3.0 port
        - WiFi connectivity
    - Confirmed models: 
        - [Surface Pro](https://www.microsoft.com/en-us/surface/devices/surface-pro/overview)
- Other suggested equipment
    - Long power extension cable and/or power strip
    - USB flash drive
    - USB mouse
    - USB hub (if USB ports on the laptop are limited)

## Software/Services

The main piece of software you'll want to acquire is
[OBS Studio](https://obsproject.com/). OBS is free and open-course, and
comes equipped to stream to YouTube out-of-the-box. It may be downloaded
to your computer at that link.

Speaking of [YouTube](https://www.youtube.com/), we recommend you
use Google's video service to stream, as you will have very little configuration
to figure out, and your streams will automatically be archived as
YouTube videos. If you already have a Google account (not a Google Apps account,
e.g. your university email may not work), you should be able to log into your
[Live Dashboard](https://www.youtube.com/live_dashboard). Under "Encoder Setup",
reveal and copy your "Stream name/key" to be pasted into OBS later.
(Treat this key like a password and only reveal it to people you trust!)

When you first start OBS Studio, you should be able to choose to set up YouTube streaming
and enter this key. Alternately, go to `File>Settings>Stream` and choose

- Stream Type: `Streaming Services`
- Service: `YouTube / YouTube Gaming`,
- Server: `Primary YouTube ingest server`

and then enter your stream key in the provided field.

Next, you'll need to create four "Scenes" with the following suggested "Sources".
Note that you'll need to connect your camera to the laptop before you can
configure everything. I recommend doing this in the same or similar venue
to where you plan to stream the first time, so you can also figure out
a good place to position the camera to capture audio and video.

- Title Card: A scene with the name of your event to use before/after/between
  speakers.
    - Title: A Text source to dislpay your event title. I suggest using
      white text with a black outline.
    - Background: either an Image source or a Color source to fill the
      background with something more interesting than solid blackness.
- Slides and Video: The default scene to display both the speaker and their
  slides.
    - Title (small): A Text source to display your event title,
      with a smaller font than on your Title Card.
    - Speaker Name: A Text source to display your speaker's name.
    - Slides: Window Capture source pointed at your PDF/presentation reader 
      (you'll need to open the reader first).
    - Camera Audio: Audio Capture Device source from your HDMI Input to hear
      your speaker
    - Camera Video: Video Capture Device source from your HDMI Input to display
      your speaker
    - Background: reused from Title Card
- Slides Fullscreen: A scene to switch to for intricate slides.
    - Slides: reused from Slides and Video
    - Camera Audio: reused from Slides and Video
- Video Fullscreen: A scene to switch to when focusing on speaker (e.g. writing
  on physical whiteboard)
    - Camera Video: reused from Slides and Video
    - Camera Audio: reused from Slides and Video

For each scene, you can resize and reposition video sources as desired.
Higher listed sources overlay the sources lower on your list, so
click/drag their names on the list to rearrange.

For an example of me using all four types of scenes (and running the stream
myself while I gave a talk... not recommended!) check out my presentation 
<https://youtu.be/iuNZWllVDKg?t=1h4m54s> at STDC 2018.

<iframe width="560" height="315" src="https://www.youtube.com/embed/iuNZWllVDKg?start=3894" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

Once everything is set up and looks good locally, try a test stream.
You should be able to just tap "Start Streaming" to get things started,
and tap on different Scene names to switch what's being broadcast.
The stream is visible on your YouTube channel's page whenever you are live.
You can also embed a video on a webpage using the following HTML snippet:

```
<iframe width="560" height="349" src="https://www.youtube.com/embed/live_stream?channel=REPLACE-ME-WITH-YOUR-CHANNEL-ID" frameborder="0" allowfullscreen></iframe>
```

Replace `REPLACE-ME-WITH-YOUR-CHANNEL-ID` with the ID found at
<https://www.youtube.com/account_advanced> when you are logged in.

**Warning:** YouTube is pretty vigilant about automatically detecting
"spam" videos and penalizing their accounts. Any test streams will be
archived, so you should be careful to delete such videos.
(I have been penalized for this, but was able to nicely explain
the situation and have the penalty removed... better to avoid the
situation altogether though!)

## Personnel/Logistics

Running the stream generally is pretty easy; as you can see from my video
linked above, it's completely possible to run the stream *and* give
the talk yourself if necessary. But of course, it's not recommended.

For streaming mathematical presentations, I encourage you to find two
advanced undergraduate math majors or beginning graduate math students.
Such students should be interested in learning more mathematics and
finding out what a professional meeting of mathematicians involves,
but may not have the coursework or experience necessary to appreciate much of
an advanced research talk. However, we all have to start somewhere, and
a fifty-minute presentation of niche cutting-edge mathematical results
is much more palatable when you have a job to do. My students who
supported the streaming of STDC 2018 had not even taken a formal course
in topology, but reported high satisfaction with the experience. I can
corraborate the benefits their participation provided based upon the
quality of discussion we had between talks and on the road back home
from the conference.

By design, the configuration I've developed for streaming does not impact
how presenters give talks. In particular, the technology used by speakers
to display and move through slides (not outlined here) 
is completely separate from the streaming technology. But in order
to stream full-quality slides online, the speaker should provide the
videography crew a duplicate copy of their slides before their talk begins.
I recommend having a dedicated email address to send presentations to,
open on the streaming laptop.

Two people are recommended for each stream: one to operate the camera to
keep its camera (and importantly, microphone) pointed at the speaker
throughout the talk, and another to operate the laptop and OBS Studio.
This second operator is responsible for moving through the slides
along with the speaker as closely as possible. In the case of any
situation where the speaker's slides cannot be reflected in the stream,
the "Fullscreen Video" Scene may be used to capture the contents
of the projected material as much as possible.

It's recommended that these students also provide the technology
support for the presenting computer in the room. But if you have a
separate person for that position, make sure they communicate with
your videography crew to make sure slides are made available.

A strong WiFi connection is crucial for live-streaming your event.
If you cannot successfully run a test stream using your campus
WiFi network, you can choose to "record" rather than "stream". This
will create a video file stored on your local computer, which may
be uploaded to YouTube later for viewing on demand.

Finally, **get permission from your presenters before putting them online**. 
If you cannot get
written confirmation, I recommend using the phrasing, "Do you mind
being featured on the livestream of this conference/seminar for
people who could not attend in person?" In my experience, most
presenters are happy to consent, but of course you should respect their 
wishes if they are not interested.

## Consulting

Hopefully the information above is sufficient to get you up and running!
But if you have a budget and are interested in direct help from myself
to make a quality livestream and archive of your mathematical research
event, feel free to contact me at <sclontz@southalabama.edu> and
let's see what we can do!
