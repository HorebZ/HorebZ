<img src="https://my-badges.github.io/my-badges/fix-2.png" alt="I did 2 sequential fixes." title="I did 2 sequential fixes." width="128">
<strong>I did 2 sequential fixes.</strong>
<br><br>

Commits:

- <a href="https://github.com/HorebZ/Planche/commit/84ed7bc3e11b28ca401c64a5eaa92fc096ade037">84ed7bc</a>: fix(app): the card stays where it is dropped, and slides back on failure

From the live test of the drag:
- The dropped card slid back to its origin, then settled at the drop.
  The overlay no longer animates on its own: the card slides from where
  it was released to its slot (FLIP, 200 ms).
- A refused move slides the card from where it was dropped back to its
  origin, with the same motion, in place of the view transition.
- "Pending" shows on the card where it was dropped, until GitHub
  acknowledges the move, online too.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
- <a href="https://github.com/HorebZ/Planche/commit/618ed13f8da3d4c01261a4e0d5e2c367b7043221">618ed13</a>: fix(app): dispatch_intent answers with the move, even when it fails fast

The command read the board after asking the engine to flush. A refusal
that comes at once, like PLANCHE_FAULT=fail_mutations, had already
dropped the row, so the reply showed the card back at its origin before
the front heard of the failure. The board is now read before the flush.
The app also logs each mutation on stdout, like planche sync --watch.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>