Swirling-of-Life
================
$ git config --global user.name "Bee Thakore"
Code to generate parametric snowflakes for my sister's personalised birthday sculpture - in form of her own swirling of life

Manipulate[
 ParametricPlot[
  Evaluate@{{x1[a, b, c, t], y1[a, b, c, t]}, {x1[a, b, c, t], 
     y1[a, b, c, t]}}, {t, 0, .0001 + (tm 4 \[Pi])}, 
  PlotStyle -> {{clr2, Thickness[.001 + .05 thick]}, {clr3, 
     Thickness[.001 + .01 thick]}}, Axes -> False, PlotPoints -> 200,
  PlotRange -> 3, Background -> clr1],
 
 "stretch",
 {{a, 1.5, ""}, -1.5, 1.5, ImageSize -> Medium},
 "twist",
 {{b, 7.5, ""}, 1.5, 15 , .5, ImageSize -> Medium},
 "wiggle",
 {{c, 0, ""}, 0, 1.5, ImageSize -> Medium},
 Delimiter,
 "thickness",
 {{thick, .42, "" }, .04, .5 },
 "length",
 {{tm, 1, ""}, 0, 1, ImageSize -> Medium},
 Delimiter,
 "background",
 {{clr1, RGBColor[0.7, 0., 0.065], ""}, Red}, Spacer[{1, 5}],
 "frost",
 {{clr2, RGBColor[0.86, 0.715, 0.35], ""}, Red}, Spacer[{1, 5}],
 "outline",
 {{clr3, RGBColor[1, 1, 1], ""}, Red},
 
 TrackedSymbols :> {a, b, c, thick, tm, clr1, clr2, clr3},
 Initialization :> (
   x1[a_, b_, c_, t_] :=  
    Sin[.5 t] - a Sin[b t]*Cos[t] - .1 c Sin[10 b t];
   y1[a_, b_, c_, t_] :=  
    Cos[.5 t] - a Sin[b t]*Sin[t] - .1 c Cos[10 b t]; 
   ), SynchronousUpdating -> False]
