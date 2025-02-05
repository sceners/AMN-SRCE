  Hi folks, this is Tran typing... This is the virtual reality source from
the Amnesia demo. It is not compilable because we make special provisions for
our code. And because it has been so long since I wrote it, that even I would
not attempt to compile this demo again. Oh well, but if you want to look, feel
free. I had better explain a few things though:

) This is all integer math, no IEEE floating points anywhere...

) The SIN/COS table is merely a table of SIN/COS values for 512 points along
   the curve scaled from -1.0 ... 1.0 floating to -512 ... 512 integer.

) This thing loads external data, none of which is present here (or anywhere
   in existance anymore for that matter)... So if something looks like its
   missing, it probably is.

) Ignore the stars, what you want is the solid temple thingy. If I remember
   right, then here's how the sequence for that goes:

    ) All world coordinates are rotated and translated.
    ) Facets are built from the world coordinates and clipped to a plane
       at Z=5 at the same time.
    ) The facets are sorted by a sortof distance from viewpoint thingy to
       avoid having to take the square root. (Now that I think about it, why
       didn't I just sort by dX^2+dY^2+dZ^2, I didn't have to take the sqrt).
       The sort is in a byte indexed linked list to keep the data moves to a
       minimum.
    ) The thing is then projected.
    ) Finally, all visible facets are drawn. Visibility is determined by
       vektor cross products AFTER projection. (Dave's idea)

) Keep in mind this is flat mem, so don't panic if U C big pointers that
   even Windows would not allow and no seg overrides anywhere.


  Oh well, thats all I remember I think. If you really want to learn, get a
book. (A college textbook is best, you can then learn in a month what you
would normally have to pay a few thousand dollars to get a piece of paper
that says you know it in 4-6 years.)

  Ignore the SQRT routine down at the bottom, or use it, it is not part of
the source, but I remember how hard it was for me to devise one, so here you
go. (Oh yeah, this is integer too.)
