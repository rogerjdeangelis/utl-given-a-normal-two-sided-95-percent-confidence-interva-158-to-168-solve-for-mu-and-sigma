# utl-given-a-normal-two-sided-95-percent-confidence-interva-158-to-168-solve-for-mu-and-sigma
Given a normal two sided 95 percent confidence interva 158 to 168 solve for mu and sigma
    %let pgm=utl-given-a-normal-two-sided-95-percent-confidence-interva-158-to-168-solve-for-mu-and-sigma;

    Given a normal two sided 95 percent confidence interva 158 to 168 solve for mu and sigma

    Stat 101

    github                                                                                                                         
    https://tinyurl.com/49pxrb3t                                                                                                   
    https://github.com/rogerjdeangelis/utl-given-a-normal-two-sided-95-percent-confidence-interva-158-to-168-solve-for-mu-and-sigma

    /*               _     _
     _ __  _ __ ___ | |__ | | ___ _ __ ___
    | `_ \| `__/ _ \| `_ \| |/ _ \ `_ ` _ \
    | |_) | | | (_) | |_) | |  __/ | | | | |
    | .__/|_|  \___/|_.__/|_|\___|_| |_| |_|
    |_|

    */
           Three Solutions

               1 manual algebriac
               2 python sympy
               3 r (nice example of a r function and general solution)

    https://github.com/rogerjdeangelis/utl-solve-a-system-of-simutaneous-equations-r-python-sympy

    /**************************************************************************************************************************/
    /*                                    |                                                   |                               */
    /*                 INPUT              |            PROCESS                                |    OUTPUT                     */
    /*  MANUALLY                          |                                                   |                               */
    /*                                    |                                                   |                               */
    /*  95% Confidence interval (158,163) | Algebraic solution.                               |  mu=163 sigma=2.55            */
    /*  Normal distribution solve for     | Definition of 95% confidence interval             |                               */
    /*  theoretical mean and sigma        |                                                   |                               */
    /*                                    |    (158 - mu) / sigma = -1.96                     |                               */
    /*              .025    .975          |    (168 - mu) / sigma = +1.96                     |                               */
    /*                                    |                                                   |                               */
    /*     95% CI   (158,   168)          | Multiplying both sides by sigma                   |                               */
    /*                                    |                                                   |                               */
    /*                                    |                                                   |                               */
    /*                                    |     158 - mu / sigma = -1.96 * sigma              |                               */
    /*                                    |     168 - mu / sigma = +1.96 * sigma              |                               */
    /*                                    |                                                   |                               */
    /*                                    | Adding                                            |                               */
    /*                                    |                                                   |                               */
    /*                                    |     (158 - mu)+(168 - mu) = 0                     |                               */
    /*                                    |                                                   |                               */
    /*                                    |     326 - 2*mu = 0                                |                               */
    /*                                    |                                                   |                               */
    /*                                    |     mu = 163                                      |                               */
    /*                                    |                                                   |                               */
    /*                                    | Substituting mu in second equation                |                               */
    /*                                    |                                                   |                               */
    /*                                    |     (168 - 163) / sigma = +1.96                   |                               */
    /*                                    |          5              =  1.96* sigma            |                               */
    /*                                    |          5/1.96         =  sigma                  |                               */
    /*                                    |                                                   |                               */
    /*                                    |          2.55           =  sigma                  |                               */
    /*                                    |                                                   |                               */
    /*------------------------------------|---------------------------------------------------|-------------------------------*/
    /*                                    |                                                   |                               */
    /*  SYMPY                             |   %symdel frompy / nowarn;                        |  %put &=frompy;               */
    /*                                    |                                                   |                               */
    /*                                    |   %utl_submit_py64_310x('                         |  FROMPY=[{x: 163, y: 2.55}]   */
    /*                                    |   import pyperclip;                               |                               */
    /*                                    |   from sympy import solve;                        |                               */
    /*                                    |   from sympy.abc import x, y;                     |                               */
    /*                                    |   res=solve([(158 - x) / y + 1.96                 |                               */
    /*                                    |             ,(168 - x) / y - 1.96]                |                               */
    /*                                    |              , x, y, dict=True);                  |                               */
    /*                                    |   print(res);                                     |                               */
    /*                                    |   pyperclip.copy(str(res));                       |                               */
    /*                                    |   ',return=fromPy);                               |                               */
    /*                                    |                                                   |                               */
    /*                                    |   %put &=frompy;                                  |                               */
    /*                                    |                                                   |                               */
    /*------------------------------------|---------------------------------------------------|-------------------------------*/
    /*                                    |                                                   |                               */
    /*  R                                 |   General uses R function                         |          mu      sigma        */
    /*                                    |                                                   |  163.000000   2.551067        */
    /*                                    |   %utl_rbegin;                                    |                               */
    /*                                    |   parmcards4;                                     |                               */
    /*                                    |   est <- function(q, alpha) {                     |                               */
    /*                                    |     beta <- qnorm(alpha)                          |                               */
    /*                                    |     setNames(solve(cbind(1, beta), q)             |                               */
    /*                                    |     , c("mu", "sigma"))                           |                               */
    /*                                    |     }                                             |                               */
    /*                                    |   arg <- est(c(158, 168), c(0.025, 0.975))        |                               */
    /*                                    |   arg                                             |                               */
    /*                                    |   ;;;;                                            |                               */
    /*                                    |   %utl_rend;                                      |                               */
    /*                                    |                                                   |                               */
    /*                                    |                                                   |                               */
    /*                                    |                                                   |                               */
    /*                                    |                                                   |                               */
    /**************************************************************************************************************************/

    /*              _
      ___ _ __   __| |
     / _ \ `_ \ / _` |
    |  __/ | | | (_| |
     \___|_| |_|\__,_|

    */
