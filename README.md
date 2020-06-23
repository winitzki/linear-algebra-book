# linear-algebra-book
The full source code and hyperlinked PDF of the book "Linear Algebra via Exterior Products" (2010, 2020)

The latest version of the book is 1.3 (updated June 2020).

The PDF file also contains the source code inside it.

The book is printed by lulu.com [http://www.lulu.com/content/paperback-book/linear-algebra-via-exterior-products/7467754](http://www.lulu.com/content/paperback-book/linear-algebra-via-exterior-products/7467754) and is published
under the GNU Free Documentation License. The sub-directory `linalg-src` contains the full source code of the book, including LyX, LaTeX, and graphics files, as well as a Makefile with build scripts.

To build all files, run `make clean all`.

# Errata

[Errata for version 1.2](ERRATA.md)

These errata are already corrected in the current version 1.3.

## Description

### Back-cover text


This book is a pedagogical introduction to the
coordinate-free approach in finite-dimensional linear
algebra, at the undergraduate level. Throughout this
book, extensive use is made of the exterior (“wedge”)
product of vectors. In this approach, the book derives,
without matrix calculations, the standard properties of
determinants, the formulas of Jacobi and Liouville, the
Cayley-Hamilton theorem, properties of Pfaffians, the
Jordan canonical form, as well as some generalizations
of these results. Every concept is logically motivated
and discussed; exercises with some hints are provided.


Sergei Winitzki received a
PhD in theoretical physics
from Tufts University, USA
(1997) and has been a researcher and part-time lecturer at universities in the
USA, UK, and Germany.

Dr. Winitzki has authored a
number of research articles and two books on
theoretical physics. This is his third book.

### Inside flap text


This book is an undergraduate-level introduction to the coordinate-free approach in
basic finite-dimensional linear algebra. The reader should be already exposed to the
elementary array-based formalism of vector and matrix calculations. Throughout this
book, extensive use is made of the exterior (anti-commutative, “wedge”) product of
vectors. The coordinate-free formalism and the exterior product, while somewhat
more abstract, provide a deeper understanding of the classical results in linear algebra.
The standard properties of determinants, the Pythagoras theorem for multidimensional volumes, 
the formulas of Jacobi and Liouville, the Cayley-Hamilton theorem, properties of Pfaffians,
the Jordan canonical form, as well as some generalizations
of these results are derived without cumbersome matrix calculations. For the benefit
of students, every result is logically motivated and discussed. Exercises with some
hints are provided.


## Table of Contents

Preface v

0 Introduction and summary 1

0.1 Notation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 1

0.2 Sample quiz problems . . . . . . . . . . . . . . . . . . . . . . . . 3

0.3 A list of results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 5

1 Linear algebra without coordinates 11

1.1 Vector spaces . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 11

1.1.1 Three-dimensional Euclidean geometry . . . . . . . . . . 11

1.1.2 From three-dimensional vectors to abstract vectors . . . 12

1.1.3 Examples of vector spaces . . . . . . . . . . . . . . . . . . 16

1.1.4 Dimensionality and bases . . . . . . . . . . . . . . . . . . 19

1.1.5 All bases have equally many vectors . . . . . . . . . . . . 24

1.2 Linear maps in vector spaces . . . . . . . . . . . . . . . . . . . . 26

1.2.1 Abstract definition of linear maps . . . . . . . . . . . . . 27

1.2.2 Examples of linear maps . . . . . . . . . . . . . . . . . . . 29

1.2.3 Vector space of all linear maps . . . . . . . . . . . . . . . 31

1.2.4 Eigenvectors and eigenvalues . . . . . . . . . . . . . . . . 31

1.3 Subspaces . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 33

1.3.1 Projectors and subspaces . . . . . . . . . . . . . . . . . . 34

1.3.2 Eigenspaces . . . . . . . . . . . . . . . . . . . . . . . . . . 34

1.4 Isomorphisms of vector spaces . . . . . . . . . . . . . . . . . . . 35

1.5 Direct sum of vector spaces . . . . . . . . . . . . . . . . . . . . . 36

1.5.1 V and W as subspaces of V ⊕ W ; canonical projections . 37

1.6 Dual (conjugate) vector space . . . . . . . . . . . . . . . . . . . . 37

1.6.1 Dual basis . . . . . . . . . . . . . . . . . . . . . . . . . . . 38

1.6.2 Hyperplanes . . . . . . . . . . . . . . . . . . . . . . . . . . 43

1.7 Tensor product of vector spaces . . . . . . . . . . . . . . . . . . . 45

1.7.1 First examples . . . . . . . . . . . . . . . . . . . . . . . . . 47

1.7.2 Example: Rm ⊗ Rn . . . . . . . . . . . . . . . . . . . . . . 48

1.7.3 Dimension of tensor product is the product of dimensions 49

1.7.4 Higher-rank tensor products . . . . . . . . . . . . . . . . 52

1.7.5 * Distributivity of tensor product . . . . . . . . . . . . . . 52

1.8 Linear maps and tensors . . . . . . . . . . . . . . . . . . . . . . . 53

1.8.1 Tensors as linear operators . . . . . . . . . . . . . . . . . 53

1.8.2 Linear operators as tensors . . . . . . . . . . . . . . . . . 55

i

Contents

1.8.3 Examples and exercises . . . . . . . . . . . . . . . . . . . 57

1.8.4 Linear maps between different spaces . . . . . . . . . . . . 60

1.9 Index notation for tensors . . . . . . . . . . . . . . . . . . . . . . 65

1.9.1 Definition of index notation . . . . . . . . . . . . . . . . . 65

1.9.2 Advantages and disadvantages of index notation . . . . 68

1.10 Dirac notation for vectors and covectors . . . . . . . . . . . . . . 69

1.10.1 Definition of Dirac notation . . . . . . . . . . . . . . . . . 69

1.10.2 Advantages and disadvantages of Dirac notation . . . . 71

2 Exterior product 73

2.1 Motivation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 73

2.1.1 Two-dimensional oriented area . . . . . . . . . . . . . . . 73

2.1.2 Parallelograms in R3 and in Rn . . . . . . . . . . . . . . 76

2.2 Exterior product . . . . . . . . . . . . . . . . . . . . . . . . . . . . 78

2.2.1 Definition of exterior product . . . . . . . . . . . . . . . . 78

2.2.2 * Symmetric tensor product . . . . . . . . . . . . . . . . . 84

2.3 Properties of spaces ∧kV . . . . . . . . . . . . . . . . . . . . . . . 85

2.3.1 Linear maps between spaces ∧kV . . . . . . . . . . . . . 87

2.3.2 Exterior product and linear dependence . . . . . . . . . . 89

2.3.3 Computing the dual basis . . . . . . . . . . . . . . . . . . 93

2.3.4 Gaussian elimination . . . . . . . . . . . . . . . . . . . . . 95

2.3.5 Rank of a set of vectors . . . . . . . . . . . . . . . . . . . . 97

2.3.6 Exterior product in index notation . . . . . . . . . . . . . 99

2.3.7 * Exterior algebra (Grassmann algebra) . . . . . . . . . . 103

3 Basic applications 107

3.1 Determinants through permutations: the hard way . . . . . . . 107

3.2 The space ∧NV and oriented volume . . . . . . . . . . . . . . . . 109

3.3 Determinants of operators . . . . . . . . . . . . . . . . . . . . . . 114

3.3.1 Examples: computing determinants . . . . . . . . . . . . 117

3.4 Determinants of square tables . . . . . . . . . . . . . . . . . . . . 120

3.4.1 * Index notation for ∧NV and determinants . . . . . . . . 124

3.5 Solving linear equations . . . . . . . . . . . . . . . . . . . . . . . 126

3.5.1 Existence of solutions . . . . . . . . . . . . . . . . . . . . 127

3.5.2 Kramer’s rule and beyond . . . . . . . . . . . . . . . . . . 129

3.6 Vandermonde matrix . . . . . . . . . . . . . . . . . . . . . . . . . 133

3.6.1 Linear independence of eigenvectors . . . . . . . . . . . 135

3.6.2 Polynomial interpolation . . . . . . . . . . . . . . . . . . 136

3.7 Multilinear actions in exterior powers . . . . . . . . . . . . . . . 137

3.7.1 * Index notation . . . . . . . . . . . . . . . . . . . . . . . . 141

3.8 Trace . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 141

3.9 Characteristic polynomial . . . . . . . . . . . . . . . . . . . . . . 145

3.9.1 Nilpotent operators . . . . . . . . . . . . . . . . . . . . . . 151

4 Advanced applications 155

ii

Contents

4.1 The space ∧N−1V . . . . . . . . . . . . . . . . . . . . . . . . . . . 155

4.1.1 Exterior transposition of operators . . . . . . . . . . . . . 155

4.1.2 * Index notation . . . . . . . . . . . . . . . . . . . . . . . . 158

4.2 Algebraic complement (adjoint) and beyond . . . . . . . . . . . 160

4.2.1 Definition of algebraic complement . . . . . . . . . . . . 160

4.2.2 Algebraic complement of a matrix . . . . . . . . . . . . . 164

4.2.3 Further properties and generalizations . . . . . . . . . . 166

4.3 Cayley-Hamilton theorem and beyond . . . . . . . . . . . . . . . 170

4.4 Functions of operators . . . . . . . . . . . . . . . . . . . . . . . . 173

4.4.1 Definitions. Formal power series . . . . . . . . . . . . . . 174

4.4.2 Computations: Sylvester’s method . . . . . . . . . . . . . 177

4.4.3 * Square roots of operators . . . . . . . . . . . . . . . . . . 182

4.5 Formulas of Jacobi and Liouville . . . . . . . . . . . . . . . . . . 187

4.5.1 Derivative of characteristic polynomial . . . . . . . . . . 191

4.5.2 Derivative of a simple eigenvalue . . . . . . . . . . . . . 192

4.5.3 General trace relations . . . . . . . . . . . . . . . . . . . . 194

4.6 Jordan canonical form . . . . . . . . . . . . . . . . . . . . . . . . 195

4.6.1 Minimal polynomial . . . . . . . . . . . . . . . . . . . . . 201

4.7 * Construction of projectors onto Jordan cells . . . . . . . . . . . 204

5 Scalar product 213

5.1 Vector spaces with scalar product . . . . . . . . . . . . . . . . . . 213

5.1.1 Orthonormal bases . . . . . . . . . . . . . . . . . . . . . . 215

5.1.2 Correspondence between vectors and covectors . . . . . 219

5.1.3 * Example: bilinear forms on V ⊕ V ∗ . . . . . . . . . . . . 221

5.1.4 Scalar product in index notation . . . . . . . . . . . . . . 222

5.2 Orthogonal subspaces . . . . . . . . . . . . . . . . . . . . . . . . 222

5.2.1 Affine hyperplanes . . . . . . . . . . . . . . . . . . . . . . 226

5.3 Orthogonal transformations . . . . . . . . . . . . . . . . . . . . . 227

5.3.1 Examples and properties . . . . . . . . . . . . . . . . . . 227

5.3.2 Transposition . . . . . . . . . . . . . . . . . . . . . . . . . 229

5.4 Applications of exterior product . . . . . . . . . . . . . . . . . . 230

5.4.1 Orthonormal bases, volume, and ∧NV . . . . . . . . . . 230

5.4.2 Vector product in R3 and Levi-Civita symbol ε . . . . . . 232

5.4.3 Hodge star and Levi-Civita symbol in N dimensions . . 234

5.4.4 Reciprocal basis . . . . . . . . . . . . . . . . . . . . . . . . 238

5.5 Scalar product in ∧kV . . . . . . . . . . . . . . . . . . . . . . . . 240

5.5.1 Scalar product in ∧NV . . . . . . . . . . . . . . . . . . . . 240

5.5.2 Volumes of k-dimensional parallelepipeds . . . . . . . . 242

5.6 Scalar product for complex spaces . . . . . . . . . . . . . . . . . 246

5.6.1 Symmetric and Hermitian operators . . . . . . . . . . . . 248

5.6.2 Unitary transformations . . . . . . . . . . . . . . . . . . . 251

5.7 Antisymmetric operators . . . . . . . . . . . . . . . . . . . . . . 251

5.8 * Pfaffians . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 254

5.8.1 Determinants are Pfaffians squared . . . . . . . . . . . . 256

iii

Contents

5.8.2 Further properties . . . . . . . . . . . . . . . . . . . . . . 258

A Complex numbers 261

A.1 Basic definitions . . . . . . . . . . . . . . . . . . . . . . . . . . . . 261

A.2 Geometric representation . . . . . . . . . . . . . . . . . . . . . . 262

A.3 Analytic functions . . . . . . . . . . . . . . . . . . . . . . . . . . . 263

A.4 Exponent and logarithm . . . . . . . . . . . . . . . . . . . . . . . 263

B Permutations 265

C Matrices 269

C.1 Definitions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 269

C.2 Matrix multiplication . . . . . . . . . . . . . . . . . . . . . . . . . 270

C.3 Linear equations . . . . . . . . . . . . . . . . . . . . . . . . . . . 273

C.4 Inverse matrix . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 274

C.5 Determinants . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 275

C.6 Tensor product . . . . . . . . . . . . . . . . . . . . . . . . . . . . 277

D Distribution of this text 279

D.1 Motivation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 279

D.2 GNU Free Documentation License . . . . . . . . . . . . . . . . . 280

D.2.1 Preamble . . . . . . . . . . . . . . . . . . . . . . . . . . . . 280

D.2.2 Applicability and definitions . . . . . . . . . . . . . . . . 280

D.2.3 Verbatim copying . . . . . . . . . . . . . . . . . . . . . . . 282

D.2.4 Copying in quantity . . . . . . . . . . . . . . . . . . . . . 282

D.2.5 Modifications . . . . . . . . . . . . . . . . . . . . . . . . . 282

D.2.6 Combining documents . . . . . . . . . . . . . . . . . . . . 284

D.2.7 Collections of documents . . . . . . . . . . . . . . . . . . 284

D.2.8 Aggregation with independent works . . . . . . . . . . . 285

D.2.9 Translation . . . . . . . . . . . . . . . . . . . . . . . . . . . 285

D.2.10 Termination . . . . . . . . . . . . . . . . . . . . . . . . . . 285

D.2.11 Future revisions of this license . . . . . . . . . . . . . . . 285

D.2.12 Addendum: How to use this License for your documents286

D.2.13 Copyright . . . . . . . . . . . . . . . . . . . . . . . . . . . 286

Index 287

iv

Preface

In a first course of linear algebra, one learns the various uses of matrices, for
instance the properties of determinants, eigenvectors and eigenvalues, and
methods for solving linear equations. The required calculations are straightforward (because, conceptually, vectors and matrices are merely “arrays of
numbers”) if cumbersome. However, there is a more abstract and more powerful approach: Vectors are elements of abstract vector spaces, and matrices
represent linear transformations of vectors. This invariant or coordinate-free
approach is important in algebra and has found many applications in science.

The purpose of this book is to help the reader make a transition to the abstract coordinate-free approach, and also to give a hands-on introduction to
exterior products, a powerful tool of linear algebra. I show how the coordinate-free approach together with exterior products can be used to clarify the
basic results of matrix algebra, at the same time avoiding all the laborious
matrix calculations.

Here is a simple theorem that illustrates the advantages of the exterior
product approach. A triangle is oriented arbitrarily in three-dimensional
space; the three orthogonal projections of this triangle are triangles in the
three coordinate planes. Let S be the area of the initial triangle, and let A,B,C
be the areas of the three projections. Then

S^2 = A^2 + B^2 + C^2.

If one uses bivectors to represent the oriented areas of the triangle and of its
three projections, the statement above is equivalent to the Pythagoras theorem in the space of bivectors, and the proof requires only a few straightforward definitions and checks. A generalization of this result to volumes of
k-dimensional bodies embedded in N-dimensional spaces is then obtained
with no extra work. I hope that the readers will appreciate the beauty of an
approach to linear algebra that allows us to obtain such results quickly and
almost without calculations.

The exterior product is widely used in connection with n-forms, which are
exterior products of covectors. In this book I do not use n-forms — instead
I use vectors, n-vectors, and their exterior products. This approach allows
a more straightforward geometric interpretation and also simplifies calculations and proofs.
To make the book logically self-contained, I present a proof of every basic
result of linear algebra. The emphasis is not on computational techniques,
although the coordinate-free approach does make many computations easier
and more elegant. The main topics covered are tensor products; exterior
products; coordinate-free definitions of the determinant det A ˆ, the trace TrA ˆ,
and the characteristic polynomial QA ˆ (λ); basic properties of determinants;
solution of linear equations, including over-determined or under-determined
systems, using Kramer’s rule; the Liouville formula det expA ˆ = exp TrA ˆ as an
identity of formal series; the algebraic complement (cofactor) matrix; Jacobi’s
formula for the variation of the determinant; variation of the characteristic
polynomial and of eigenvalue; the Cayley-Hamilton theorem; analytic functions of operators; Jordan canonical form; construction of projectors onto Jordan cells; Hodge star and the computation of k-dimensional volumes through
k-vectors; definition and properties of the Pfaffian PfA ˆ for antisymmetric operators A ˆ. All these standard results are derived without matrix calculations;
instead, the exterior product is used as a main computational tool.

This book is largely pedagogical, meaning that the results are long known,
and the emphasis is on a clear and self-contained, logically motivated presentation aimed at students. Therefore, some exercises with hints and partial
solutions are included, but not references to literature. I have tried to avoid
being overly pedantic while keeping the exposition mathematically rigorous.
Sections marked with a star ∗ are not especially difficult but contain material that may be skipped at first reading. (Exercises marked with a star are
more difficult.)

The first chapter is an introduction to the invariant approach to vector
spaces. I assume that readers are familiar with elementary linear algebra in
the language of row/column vectors and matrices; Appendix C contains a
brief overview of that material. Good introductory books (which I did not
read in detail but which have a certain overlap with the present notes) are
“Finite-dimensional Vector Spaces” by P. Halmos and “Linear Algebra” by J.
Hefferon (the latter is a free book).

I started thinking about the approach to linear algebra based on exterior
products while still a student. I am especially grateful to Sergei Arkhipov,
Leonid Positselsky, and Arkady Vaintrob who have stimulated my interest
at that time and taught me much of what I could not otherwise learn about
algebra. Thanks are also due to Prof. Howard Haber (UCSC) for constructive
feedback on an earlier version of this text.

In the first 10 years since I made this book available for free, many readers sent me corrections to the text. For that, I thank Gabriel Aguirre, Pablo Dominguez, Joseph Ferrara, Andrew J. Ho, Yuxi Liu, Christophe Louargant, Jiri Matousek, Dmitri Pavlov, and Michele Zaffalon. Version 1.3 (prepared in June 2020) incorporates these corrections.


