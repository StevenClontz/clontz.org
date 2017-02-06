---
layout:     post
title:      "Markov Strategies in Selection Games"
subtitle:   "Seminar talk at Auburn University"
date:       2017-02-05 19:54:00
header-img: "img/math-bg.png"
---

Here is an outline of the talk I gave at the AU set-theoretic topology
seminar on 2017 Feb 06.

- Definition of the [Banach-Mazur Game][bmgame]:
    - Introduced by Mazur as Problem 43 of the [Scottish Book][scotbook]
      [[pdf]][scotpdf], a notebook kept by mathematicians frequenting
      the Scottish Cafe in Lwów, Poland in the 1930s and 1940s.
    - Let \\(S\subseteq\mathbb R\\). Two players alternate choosing
      decreasing intervals
      \\(N_0\supseteq E_0\supseteq N_1\supseteq E_1\supseteq\dots\\).
      The first player wins if \\(\bigcap_{n<\omega}N_n\\) contains a point of
      \\(S\\); the first player wins otherwise.
    - Banach (1935) showed that the second player has a winning strategy for
      this game if and only if \\(S\\) is *meager*, a countable union
      of nowhere-dense sets. The prize was a bottle of wine, awarded by Mazur.
    - Our variant of interest: two players choose  
      decreasing non-empty open subsets
      \\(E_0\supseteq N_0\supseteq E_1\supseteq N_1\supseteq\dots\\)
      of a topological space \\(X\\), and let the *second* player win if and
      only if \\(\bigcap_{n<\omega}N_n\not=\emptyset\\).
      Call this game \\(BM(X)\\).
- Limited information strategies
    - Let \\(M\\) be a set of possible moves for a game.
    - A (perfect information) strategy is a function
      \\(\sigma:M^{<\omega}\to M\\) that determines the next move for a player
      based upon all the previous moves of her opponent.
    - A \\(k\\)-tactical strategy is a function
      \\(\sigma:M^{\leq k}\to M\\) that determines the next move for a player
      based upon the most recent \\(k\\) previous moves of her opponent.
    - A \\(k\\)-Markov strategy is a function
      \\(\sigma:M^{\leq k}\times\omega\to M\\)
      that determines the next move for a player
      based upon the most recent \\(k\\) moves of her opponent and the current
      round number.
    - A coding strategy is a function
      \\(\sigma:M^{\leq 2}\to M\\)
      that determines the next move for a player
      based upon the most recent moves of both players.
    - A strategy is *winning* if a player that follows the strategy is
      guaranteed to win the game regardless of the moves of the opponent.
    - A winning (perfect information) strategy for the second player in
      \\(BM(X)\\) may always be improved to a winning coding strategy.
      (Debs 1985; Galvin,Telgarsky 1986)
    - A winning Markov (that is, \\(1\\)-Markov)
      strategy for the second player in
      \\(BM(X)\\) may always be improved to a winning tactical
      (that is, \\(1\\)-tactical, also known as stationary) strategy.
      (Galvin,Telgarsky 1986)
    - Debs (1985) found examples of spaces for which the second player
      in \\(BM(X)\\) has winning
      (\\(2\\)-tactical; see Bartoszynski,Scheepers,Just 1993)
      strategies, but no winning tactical strategies.
    - [Telgarksy conjectures (1987)][telgarksy]
      that there exist spaces \\(X_k\\) for \\(k<\omega\\)
      such that the second player in
      \\(BM(X_k)\\) has a winning \\((k+1)\\)-tactical
      strategy, but no winning \\(k\\)-tactical strategy.
- Countable/Finite Games
    - Scheepers (1992) published the first of many papers under the
      title of *Meager-Nowhere Dense Games: \\(n\\)-Tactics*.
    - Let \\(MG(X)\\) be a game where the first player
      chooses meager subsets \\(M_{n+1}\supseteq M_n\\) during round \\(n+1\\),
      followed by the second player choosing a nowhere dense subset
      \\(N_{n+1}\\). The second player wins if
      \\(\bigcup_{n<\omega}N_n\supseteq\bigcup_{n<\omega}M_n\\).
    - The special case where \\(X=\kappa\\) is a discrete space
      (and therefore the first player chooses countable sets and the second
      player chooses finite sets) was studied by Scheepers in
      *Concerning \\(n\\)-tactics in the countable-finite game*.
      Call this game \\(Sch^{\cup,\supsetneq}(\kappa)\\).
    - Scheepers showed that any \\((k+3)\\)-tactical strategy for the second
      player in \\(Sch^{\cup,\supsetneq}(\kappa)\\)
      may be improved to a \\(k\\)-tactical strategy.
    - Modification: \\(Sch^{\cap}(\kappa)\\): the first player chooses
      any countable set \\(C_n\\), and the second player chooses any finite set
      \\(F_n\\). The second player wins if
      \\(\bigcup_{n<\omega}F_n\supseteq\bigcap_{n<\omega}C_n\\).
    - The axiom \\(\mathcal A'(\kappa)\\) implies that the second player
      has a winning \\(2\\)-tactical strategy in
      \\(Sch^{\cup,\supsetneq}(\kappa)\\) (Scheepers) and
      a winning \\(2\\)-Markov strategy in
      \\(Sch^{\cap}(\kappa)\\) (Clontz).
    - \\(A'(\aleph_n)\\) holds in ZFC for \\(n<\omega\\) (Clontz,Dow to appear);
      \\(A'(\kappa)\\) may be forced to hold for arbitrarily large
      \\(\kappa\leq\mathfrak c\\) (Scheepers).
- Selection Games
    - Let \\(G_{fin}(\mathcal A,\mathcal B)\\)
      be the game where the first player chooses
      \\(A_n\in \mathcal A\\) and the second player chooses a finite subset
      \\(B_n\in[A_n]^{<\omega}\\). The second player wins if
      \\(\bigcup_{n<\omega}B_n\in\mathcal B\\).
    - For each cardinal \\(\kappa\\), let \\(L(\kappa)=\kappa\cup\\{\infty\\}\\)
      be the space with \\(\kappa\\) discrete and \\(\infty\\) having
      co-countable neighborhoods.
    - Let the Menger game be
      \\(Men(X)=G_{fin}(\mathcal O,\mathcal O)\\) where \\(\mathcal O\\)
      is the set of open covers of \\(X\\).
    - In regards to \\(k\\)-Markov strategies for the second player,
      \\(Men(L(\kappa))\\) and \\(Sch^{\cap}(\kappa)\\) are equivalent
      (Clontz).
- Markov strategies in Selection Games
    - Any \\((k+2)\\)-Markov strategy for the second player in
      \\(G_{fin}(\mathcal A,\mathcal B)\\) may be improved to a
      \\(2\\)-Markov strategy.
        - Source: [Applications of limited information strategies in Menger's game (to appear, CUMC)][applications]
    - Assume \\(\|\bigcup\mathcal A\|\leq\aleph_0\\) and \\(\mathcal B\\)
      is closed under supersets. Then any winning (perfect-information)
      strategy for the second player in \\(G_{fin}(\mathcal A,\mathcal B)\\)
      may be improved to a Markov strategy.
        - Source: [Relating games of Menger, countable fan tightness, and selective separability (preprint)][preprint]
    - Corollaries:
        - Let \\(\mathcal D\\) give the dense subsets of a space \\(X\\).
          The second player having a winning strategy in
          \\(G_{fin}(\mathcal D,\mathcal D)\\) characterizes
          strategic selective separability, \\(SS^+\\). Thus all countable
          \\(SS^+\\) spaces are Markov selectively separable, \\(SS^{+mark}\\).
          (Barman,Dow 2012).
        - The second player having a winning strategy in
          \\(G_{fin}(\mathcal O,\mathcal O)\\) characterizes the
          strategic Menger property.
          All second-countable strategic Menger spaces are Markov Menger.
          Markov Menger spaces are exactly the
          \\(\sigma\\)-relatively-compact spaces
          (equivalent to \\(\sigma\\)-compact for regular spaces). (Clontz)
    - Question (Gruenhage): Does there exist an \\(SS^+\\) space that is not
      \\(SS^{+mark}\\)?


[bmgame]: https://en.wikipedia.org/wiki/Banach%E2%80%93Mazur_game
[scotbook]: https://en.wikipedia.org/wiki/Scottish_Book
[scotpdf]: http://kielich.amu.edu.pl/Stefan_Banach/pdf/ks-szkocka/ks-szkocka3ang.pdf
[telgarksy]: http://www.telgarsky.com/1987-RMJM-Telgarsky-Topological-Games.pdf
[applications]: https://www.researchgate.net/publication/282155672_Applications_of_limited_information_strategies_in_Menger%27s_game
[preprint]: https://www.researchgate.net/publication/309202868_Relating_games_of_Menger_countable_fan_tightness_and_selective_separability
