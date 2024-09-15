# BCDimension
Computing the dimension of Base Change subspaces of Bianchi modular forms 

By Alexander D. Rahm and Panagiotis Tsaknias

Spaces of Bianchi modular forms can be computed using the action of a Bianchi group on 3-dimensional hyperbolic space. On 

https://melodia.gaati.org/open-data/BianchiModularForms.html

you can download the dimension tables computed in an Irish Centre for High-End Computing (ICHEC) project by Alexander D. Rahm and Mehmet Haluk Sengun. In this project, we have calculated the dimensions of the spaces of cuspidal Bianchi modular forms, locating several of the very rare instances that are not lifts of elliptic modular forms. Elliptic modular forms are the subject of the now proven Taniyama--Shimura conjecture. A part of this proof has allowed to complete Fermat's Last Theorem, which has been a challenge to mathematics for over 300 years. The Taniyama--Shimura conjecture is nowadays called the modularity theorem, and attaches an elliptic curve to each classical modular form (so to call it an "elliptic" modular form), corresponding via the L-series. There are deep number-theoretical reasons for expecting that this kind of correspondence can extend to the Bianchi modular forms, attaching Abelian varieties to them (elliptic curves are one-dimensional Abelian varieties). Bianchi modular forms over an imaginary quadratic field K are automorphic forms of cohomological type associated to the Bianchi group of K, the latter being the rank two special linear group over the ring of integers in K. Even though modern studies of Bianchi modular forms go back to the mid 1960's, most of the fundamental problems surrounding their theory are still wide open. Using the software released here, we have extended our published computations of cuspidal Bianchi modular forms (

http://fr.arxiv.org/abs/1104.5303

appeared in LMS J. Comp. & Math), that were carried out on "workstation" machines exclusively for the subgroup level 1 (i.e. the full Bianchi groups), to a large scope of congruence subgroups: 

http://hdl.handle.net/10993/29493

For the subgroup level 1, we have already discovered several instances of particluar interest, namely Bianchi modular forms that are not lifts from the elliptic modular forms via the Langlands base change procedure. There are so far no theoretical predictions available on the occurrence of such non-lifted forms, so to make the numerical results very valuable. The L-functions and Modular Forms Data-Base (LMFDB) has accepted this data for publication.

The MAGMA source code of the involved base change dimension computations is provided here, in the code package BCDimension, covered by the GNU GPL licence v.3.0. The core functions have been written by Panagiotis Tsaknias, and the surrounding functions by Alexander D. Rahm.

Running the command

magma Eisenstein_conversion.m

from the unpacked folder produces a table with columns

Discriminant | levelHNF | weight | total | all cuspidal | new cuspidal | newBC | newCM+genuine

To work over a different imaginary quadratic field, the user may edit the source file in order to process a different input table from column (I.) of
https://melodia.gaati.org/open-data/BianchiModularForms.html
Attention: Only prime discriminant > 3 is implemented correctly.

Alternatively, the user may start by loading

magma BaseChangeDimension.txt

and then apply the function BCD manually to an imaginary quadratic field and a weight.

The function BCD:=function(d,n) takes input d the discriminant of the imaginary quadratic number field (again, only prime discriminants > 3 may be used), or a negative integer whose square root generates the number field and n the automorphic weight (trivial weight is 2); it outputs the base change dimension of the level one modular forms space at discriminant d and weight n.

Examples:

> BCD(-5,2);

1

> BCD(-5,4);

3

> BCD(-5,10);

9

> BCD(-20,2);

1

> BCD(-20,4);

3

> BCD(-20,10);

9

We acknowledge the funding of the principal investigators by the Irish Research Council as well as the ANR project MELODIA (for Alexander D. Rahm) and by the Marie Curie program (for Mehmet Haluk Sengun).

