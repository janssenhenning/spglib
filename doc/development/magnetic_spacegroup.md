# Magnetic space group (MSG)

## Definition

For more details, we refer to Refs. {cite}`litvin2014magnetic,Campbell:ib5106`.

A **magnetic space group** {math}`\mathcal{M}` is a subgroup of direct product of space group {math}`\mathcal{G}` and {math}`\mathbb{Z}_{2} \simeq \{1, 1' \}`.

A **family space group** (FSG) {math}`\mathcal{F}(\mathcal{M})` is a non-magnetic space group obtained by ignoring primes in operations,

```{math}
    \mathcal{F}(\mathcal{M}) = \left\{ (\mathbf{R}, \mathbf{v}) \mid (\mathbf{R}, \mathbf{v}) \in \mathcal{M} \vee (\mathbf{R}, \mathbf{v})1' \in \mathcal{M} \right\}.
```

A **maximal space subgroup** (XSG) {math}`\mathcal{D}(\mathcal{M})` is a space group obtained by removing primed operations,

```{math}
    \mathcal{D}(\mathcal{M}) = \left\{ (\mathbf{R}, \mathbf{v}) \mid (\mathbf{R}, \mathbf{v}) \in \mathcal{M} \right\}.
```

Magnetic space groups are classified to the following four types \[^notation\]:

- (type-I) {math}`\mathcal{M} \simeq \mathcal{F}(\mathcal{M}) \simeq \mathcal{D}(\mathcal{M})`.
- (type-II) {math}`\mathcal{M} \simeq \mathcal{F}(\mathcal{M}) \times \{1, 1'\}, \mathcal{F}(\mathcal{M}) \simeq \mathcal{D}(\mathcal{M})`.
- (type-III)
  {math}`\mathcal{D}(\mathcal{M})` is a translationengleiche subgroup of index two of {math}`\mathcal{F}(\mathcal{M})`.
  ```{math}
    \mathcal{M} \simeq \mathcal{D}(\mathcal{M}) \sqcup (\mathcal{F}(\mathcal{M}) \backslash \mathcal{D}(\mathcal{M})) 1'
  ```
- (type-IV)
  {math}`\mathcal{D}(\mathcal{M})` is a klessengleichesubgroup of index two of {math}`\mathcal{F}(\mathcal{M})`.
  ```{math}
    \mathcal{M} \simeq \mathcal{D}(\mathcal{M}) \sqcup (\mathcal{F}(\mathcal{M}) \backslash \mathcal{D}(\mathcal{M})) 1'
  ```

\[^notation\]: {math}`A \backslash B` represents the set difference, which is a set of elements in {math}`A` which are not element of {math}`B`.
{math}`A \sqcup B` represents union of disjoint sets {math}`A` and {math}`B`.

```{list-table} Number of (3-dimensional) magnetic space groups
:header-rows: 1

* - type-I
  - type-II
  - type-III
  - type-IV
  - Total
* - 230
  - 230
  - 674
  - 517
  - 1651
```

For type-I, II, III MSG, both OG and BNS symbols use a setting of {math}`\mathcal{F}(\mathcal{M})`.
For type-IV MSG, OG symbols use a setting of {math}`\mathcal{F}(\mathcal{M})` and BNS symbols use that of {math}`\mathcal{D}(\mathcal{M})`.

## Action of MSG operations

In general, we can arbitrarily choose how MSG operation acts on objects as long as it satisfies the definition of left actions.
Here are the examples of objects and actions on them \[^notation2\]:

- Collinear magnetic moment {math}`m_{z}` without spin-orbit coupling

  ```{math}
  (\mathbf{R}, \mathbf{v}) \circ m_{z} &= m_{z} \\
  1' \circ m_{z} &= -m_{z}
  ```

- Magnetic moment {math}`\mathbf{m}`

  ```{math}
  (\mathbf{R}, \mathbf{v}) \circ \mathbf{m} &= (\mathrm{det} \mathbf{R}) \mathbf{R} \mathbf{m} \\
  1' \circ \mathbf{m} &= -\mathbf{m}
  ```

- Grain boundary made of "black" and "white" crystals

  ```{math}
  (\mathbf{R}, \mathbf{v}) \circ (\mathbf{r}, \mathrm{black}) &= ( \mathbf{R}\mathbf{r} + \mathbf{v}, \mathrm{black} ) \\
  (\mathbf{R}, \mathbf{v}) \circ (\mathbf{r}, \mathrm{white}) &= ( \mathbf{R}\mathbf{r} + \mathbf{v}, \mathrm{white} ) \\
  1' \circ (\mathbf{r}, \mathrm{black}) &= (\mathbf{r}, \mathrm{white}) \\
  1' \circ (\mathbf{r}, \mathrm{white}) &= (\mathbf{r}, \mathrm{black}) \\
  ```

\[^notation2\]: We write action of group element {math}`g` on object {math}`x` as {math}`g \circ x`.

## MSG detection for crystal structure

Formally, `cell` consists of

- column-wise lattice matrix {math}`\mathbf{A}`
- fractional coordinates {math}`\mathbf{X}`
- atomic types {math}`\mathbf{T}`
- magmoms {math}`\mathbf{M}`

SG corresponds to the following equivalence relation (equivalent to `cel_is_overlap_with_same_type`) as {math}`\mathcal{S} := \mathrm{Stab}_{\mathrm{E}(3)} \, (\mathbf{X}, \mathbf{T}) / \sim_{\mathcal{S}}` \[^notation3\],

```{math}
    (X_{i}, T_{i}) \sim_{\mathcal{S}} (X_{j}, T_{j})
    \overset{\mathrm{def}}{\iff}
    \exists g \in \mathrm{E}(3) \, s.t. \,  g \circ X_{i} = X_{j} \,\mathrm{and}\,  T_{i} = T_{j}.
```

\[^notation3\]: {math}`\mathrm{E}(3)` is three dimensional Euclidean group.
When group {math}`G` acts on elements in {math}`X`, we write the stabilizer as {math}`\mathrm{Stab}_{G} X`.

XSG corresponds to the following equivalence relation as {math}`\mathcal{D} := \mathrm{Stab}_{ \mathcal{S} } \, (\mathbf{X}, \mathbf{T}, \mathbf{M}) / \sim_{\mathcal{D}}`,

```{math}
    (X_{i}, T_{i}, M_{i}) \sim_{\mathcal{D}} (X_{j}, T_{j}, M_{j})
    \overset{\mathrm{def}}{\iff}
    \exists g \in \mathcal{S} \, s.t. \, g \circ M_{i} = M_{j}.
```

MSG corresponds to the following equivalence relation as {math}`\mathcal{M} = \mathrm{Stab}_{ \mathcal{S} \times \{ 1, 1' \} } \, (\mathbf{X}, \mathbf{T}, \mathbf{M}) / \sim_{\mathcal{M}}`

```{math}
    (X_{i}, T_{i}, M_{i}) \sim_{\mathcal{M}} (X_{j}, T_{j}, M_{j})
    \overset{\mathrm{def}}{\iff}
    \exists g \in \mathcal{S}, \exists \theta \in \{ 1, 1' \} \, s.t. \, g \theta \circ M_{i} = M_{j}
```

{math}`\mathcal{S}` may not be index-two supergroup of {math}`\mathcal{D}` because the former ignores magmom configurations.
Thus, we compute FSG via MSG as {math}`\mathcal{F} := \mathcal{M}  / \{ 1, 1' \}`.

### Procedure to detect MSG operations

In actual implementation in `spn_get_operations_with_site_tensors`, the following steps two, three, and four are performed at the same time.

1. Compute SG {math}`\mathcal{S}` by just ignoring magmoms.
2. Compute XSG {math}`\mathcal{D}` by checking {math}`g \circ M_{i} = M_{g \circ i}` one by one for {math}`g \in \mathcal{S}`.
3. Compute MSG {math}`\mathcal{M}` by checking {math}`g \theta \circ M_{i} = M_{g \circ i}` one by one for {math}`g \theta \in \mathcal{S} \times \{ 1, 1' \}`.
4. Compute FSG {math}`\mathcal{F}` by ignoring primes in {math}`\mathcal{M}`

In `spgat_get_symmetry_with_site_tensors`, `sym_nonspin` corresponds to {math}`\mathcal{S}`.
Then, `spn_get_operations_with_site_tensors` computes {math}`\mathcal{M}` under the following actions:

- `tensor_rank=0`
  - `is_magnetic=true`: {math}`1' \circ m = -m, (\mathbf{R}, \mathbf{v}) \circ m = m`
  - `is_magnetic=false`: {math}`1' \circ m_{z} = m_{z}, (\mathbf{R}, \mathbf{v}) \circ m = m`
- `tensor_rank=1` (currently only support axial vector)
  - `is_magnetic=true`: {math}`1' \circ \mathbf{m} = -\mathbf{m}, (\mathbf{R}, \mathbf{v}) \circ \mathbf{m} = (\mathrm{det} \mathbf{R}) \mathbf{R} \mathbf{m}`
  - `is_magnetic=false`: {math}`1' \circ \mathbf{m} = \mathbf{m}, (\mathbf{R}, \mathbf{v}) \circ \mathbf{m} = (\mathrm{det} \mathbf{R}) \mathbf{R} \mathbf{m}`

## Procedure to identify MSG

`spglib.c:get_magnetic_dataset`

### Identify type of MSG and choose reference setting

1. Determine type of MSG
   - When {math}`[\mathcal{F}:\mathcal{D}] = 1`
     - {math}`[\mathcal{M}:\mathcal{F}] = 1` -> Type-I
     - {math}`[\mathcal{M}:\mathcal{F}] = 2` -> Type-II
   - When {math}`[\mathcal{F}:\mathcal{D}] = 2`
     - Find a coset decomposition {math}`\mathcal{M} = \mathcal{D} \sqcup g \mathcal{D}`
     - {math}`g` is not translation -> Type-III
     - {math}`g` is translation -> Type-IV
2. Choose reference setting
   - Type-I, II, III -> Hall symbol of {math}`\mathcal{F}`
   - Type-IV -> Hall symbol of {math}`\mathcal{D}`
3. Get transformation {math}`(\mathbf{P}, \mathbf{p})` to the reference setting by `spa_search_spacegroup_with_symmetry`.
   - Type-I, II, III: Obtain transformation {math}`(\mathbf{P}, \mathbf{p})` such that {math}`\mathcal{F}(\mathcal{M})' := (\mathbf{P}, \mathbf{p})^{-1} \mathcal{F}(\mathcal{M}) (\mathbf{P}, \mathbf{p})` is standardized.
   - Type-IV: Obtain transformation {math}`(\mathbf{P}, \mathbf{p})` such that {math}`\mathcal{D}(\mathcal{M})' := (\mathbf{P}, \mathbf{p})^{-1} \mathcal{D}(\mathcal{M}) (\mathbf{P}, \mathbf{p})` is standardized.

We denote a transformed MSG by {math}`(\mathbf{P}, \mathbf{p})` as {math}`\mathcal{M}' := (\mathbf{P}, \mathbf{p})^{-1} \mathcal{M} (\mathbf{P}, \mathbf{p})`.
Then, we try to compare {math}`\mathcal{M}'` with {math}`\mathcal{M}_{\mathrm{std}}` in database.

### When {math}`\mathcal{M}` is type-I or type-II

Just compare {math}`\mathcal{M}'` with {math}`\mathcal{M}_{\mathrm{std}}`.

### When {math}`\mathcal{M}` is type-III

By construction, we can assume {math}`\mathcal{F}(\mathcal{M}') = \mathcal{F}(\mathcal{M}_{\mathrm{std}})`.
However, this does not imply {math}`\mathcal{M}' = \mathcal{M}_{\mathrm{std}}` in general!
We also need to try a correction transformation {math}`(\mathbf{P}_{\mathrm{corr}}, \mathbf{p}_{\mathrm{corr}})` such that

```{math}
    (\mathbf{P}_{\mathrm{corr}}, \mathbf{p}_{\mathrm{corr}})^{-1} \mathcal{F}(\mathcal{M}_{\mathrm{std}}) (\mathbf{P}_{\mathrm{corr}}, \mathbf{p}_{\mathrm{corr}}) = \mathcal{F}(\mathcal{M}_{\mathrm{std}}) \\
    (\mathbf{P}_{\mathrm{corr}}, \mathbf{p}_{\mathrm{corr}})^{-1} \mathcal{D}(\mathcal{M}') (\mathbf{P}_{\mathrm{corr}}, \mathbf{p}_{\mathrm{corr}}) = \mathcal{D}(\mathcal{M}_{\mathrm{std}}).
```

For triclinic and monoclinic type-III MSGs, there is no such a conjugate XSG, {math}`\mathcal{D}' \neq \mathcal{D}_{\mathrm{std}}`, with {math}`\mathcal{D}(\mathcal{M}_{\mathrm{std}})`, because point groups of triclinic and monoclinic space groups do not have proper conjugate subgroups.

For other crystal systems, we need to compute factor group of the Affine normalizer {math}`\mathcal{N}_{\mathcal{A}}(\mathcal{F}(\mathcal{M}_{\mathrm{std}})) / \mathcal{D}(\mathcal{M}_{\mathrm{std}})`, which is a finite group in this case, and check with each operation.
Instead of
We enumerate integer matrices {math}`\mathbf{P}_{\mathrm{corr}}` whose elements are -1, 0, or 1, and determinant is equal to 1.
Also, we enumerate candidates of origin shifts {math}`\mathbf{p}_{\mathrm{corr}}` by restricting their values are one of {math}`0, \frac{1}{4}, \frac{1}{2}, \frac{3}{4}`.
These will be sufficient to cover all conjugated XSG because they cover all additional generators of Affine normalizer of space groups in standardized setting shown in ITA Table 3.5.2.5.
Because the correction transformation {math}`(\mathbf{P}_{\mathrm{corr}}, \mathbf{p}_{\mathrm{corr}})` can be tabulated for each standardized space group, we pre-compute them and store the results in `msg_database.c`.

### When {math}`\mathcal{M}` is type-IV

By construction, we can assume {math}`\mathcal{D}(\mathcal{M}') = \mathcal{D}(\mathcal{M}_{\mathrm{std}})`.
We try a correction transformation {math}`(\mathbf{P}_{\mathrm{corr}}, \mathbf{p}_{\mathrm{corr}})` as well as the type-III case.

## Standardization of magnetic crystal structure

### Procedure to idealize positions and site tensors

Suppose we have a factor group of MSG, {math}`\overline{\mathcal{M}} := \mathcal{M} / \mathcal{T}(\mathcal{M})`.
Now we consider to idealize positions and site tensors to possess the symmetry {math}`\overline{\mathcal{M}}`.
The action of {math}`\overline{\mathcal{M}}` on positions can be defined as

```{math}
    g \circ (\mathbf{x}_{1}, \dots, \mathbf{x}_{n})
    :=
    \left( g \circ \mathbf{x}_{ g^{-1} \circ i } \right)_{i=1, \cdots, n}
    \quad
    (g \in \overline{\mathcal{M}}).
```

The invariant subspace of {math}`(\mathbf{x}_{1}, \dots, \mathbf{x}_{N})` is obtained by the projection operator on the identity representation (also known as Reynolds operator) as

```{math}
    R_{\overline{\mathcal{M}}} \circ (\mathbf{x}_{1}, \dots, \mathbf{x}_{n})
    :=
    \left(
        \frac{1}{|\overline{\mathcal{M}}|} \sum_{g \in \overline{\mathcal{M}}} g \circ \mathbf{x}_{ g^{-1} \circ i }
    \right)_{i=1, \dots, n}.
```

In practice, we average out the residual to avoid rounding error as

```{math}
    R_{\overline{\mathcal{M}}} \circ (\mathbf{x}_{1}, \dots, \mathbf{x}_{n})
    =
    \left(
        \mathbf{x}_{i}
        + \frac{1}{|\overline{\mathcal{M}}|}
          \sum_{g \in \overline{\mathcal{M}}}
            \left[
                g \circ \mathbf{x}_{ g^{-1} \circ i } - \mathbf{x}_{i}
            \right]
    \right)_{i=1, \dots, n}.
```

Although we can obtain the invariant subspace by computing kernel of the above operator, we merely apply it on given positions since the positions are assumed to be close to an idealized ones.
An idealization of site tensors can be performed as well.

Note that this idealization is extension of special position operators presented in Ref. {cite}`Grosse-Kunstleve:au0265`, which considers only site-symmetry group of each site.

### Transformation of space group {math}`\mathcal{G}`

We denote a primitive lattice as {math}`L_{\mathrm{prim}}` and a conventional lattice as {math}`L_{\mathrm{conv}}`.
Here the centering vectors correspond to {math}`L_{\mathrm{conv}} / L_{\mathrm{prim}}`.
For example, trigonal space groups with hexagonal cell (obverse) give

```{math}
    L_{\mathrm{conv}} / L_{\mathrm{prim}} =
    \left\{
        (0, 0, 0),
        (2/3, 1/3, 1/3),
        (1/3, 2/3, 2/3)
    \right\}.
```

We write translation group formed by {math}`L_{\mathrm{prim}}` as {math}`\mathcal{T}_{\mathrm{prim}}`, and translation group formed by {math}`L_{\mathrm{conv}}` as {math}`\mathcal{T}_{\mathrm{conv}}`.
Space group {math}`\mathcal{G}` can be written by finite factor group {math}`\mathcal{G} / \mathcal{T}_{\mathrm{conv}}` and the centerings:

```{math}
    \mathcal{G} / \mathcal{T}_{\mathrm{prim}}
    =
    \left\{
        (\mathbf{I}, \mathbf{c}) (\mathbf{W}, \mathbf{w})
        \mid
        (\mathbf{W}, \mathbf{w}) \in \mathcal{G} / \mathcal{T}_{\mathrm{conv}},
        \mathbf{c} \in L_{\mathrm{conv}} / L_{\mathrm{prim}}
    \right\}
```

Consider a transformation matrix {math}`\mathbf{P}` (corresponds to `Spacegroup.bravais_lattice`) and origin shift {math}`\mathbf{p}` (corresponds to `Spacegroup.origin_shift`).
This transformation convert the factor group {math}`\mathcal{G} / \mathcal{T}_{\mathrm{conv}}` to

```{math}
    \left\{
        (\mathbf{P}, \mathbf{p}) (\mathbf{W}, \mathbf{w}) (\mathbf{P}, \mathbf{p})^{-1}
        \mid
        (\mathbf{W}, \mathbf{w}) \in \mathcal{G} / \mathcal{T}_{\mathrm{conv}}
    \right\}.
```

If the conventional lattice is properly chosen, each operation in {math}`\mathcal{G} / \mathcal{T}_{\mathrm{conv}}` has a unique linear part.
Then, the above transformed factor group has the same order as {math}`\mathcal{G} / \mathcal{T}_{\mathrm{conv}}`.
The centering vectors are transformed as

```{math}
    \left\{
        \mathbf{P} (\mathbf{c} + \mathbf{n}) \, \mathrm{mod}\, 1
        \mid
        \mathbf{c} \in L_{\mathrm{conv}} / L_{\mathrm{prim}}, \mathbf{n} \in \mathbb{Z}^{3}
    \right\}.
```

When {math}`|\det \mathbf{P}| = 1`, the transformed centering vectors give the same conventional lattice.
When {math}`|\det \mathbf{P}| > 1`, some centering vectors become duplicated.
When {math}`|\det \mathbf{P}| < 1`, we need to additionally find lattice points.
We can confirm the range of {math}`\mathbf{n}` to {math}`[0, d)^{3}`, where {math}`d` is maximum denominator of {math}`\mathbf{P}`.

### Transformation of magnetic space group {math}`\mathcal{M}`

Transformation of type-I MSG is trivial.
For other types, we need care for time-reversal operation in coset representatives.

```{math}
    \mathcal{M}
        &= \mathcal{D} \sqcup g \mathcal{D} \\
    \mathcal{M} / \mathcal{T}_{\mathrm{prim}}(\mathcal{M})
        &=
        \langle g \rangle
        \cdot ( \mathcal{T}_{\mathrm{conv}}(\mathcal{M}) / \mathcal{T}_{\mathrm{prim}}(\mathcal{M}) )
        \cdot ( \mathcal{M} / \langle g \rangle / \mathcal{T}_{\mathrm{conv}}(\mathcal{M}) ) \\
        &=
        \langle g \rangle
        \cdot ( \mathcal{T}_{\mathrm{conv}}(\mathcal{M}) / \mathcal{T}_{\mathrm{prim}}(\mathcal{M}) )
        \cdot ( \mathcal{D} / \mathcal{T}_{\mathrm{conv}}(\mathcal{M}) ) \\
```

Each element in factor group {math}`\mathcal{D} / \mathcal{T}_{\mathrm{conv}}(\mathcal{D})` has a unique linear part.

## Code reading on symmetry transformation

Based on `refinement.c:get_refined_symmetry_operations`

For given space group {math}`\mathcal{G}_{p}` with primitive cell, `spa_search_spacegroup_with_symmetry` gives `Spacegroup` object.

Corresponding space group {math}`\mathcal{G}_{\mathrm{std}}` in DB

Let `P := Spacegroup.bravais_lattice` (after changing basis to primitive) and `p := Spacegroup.origin_shift`.

.. math::
A\_{\\mathrm{std}} &=  A\_{p} P \\
\\mathcal{G}_{p} &= (P^{-1}, p)^{-1} \\mathcal{G}_{\\mathrm{std}} (P^{-1}, p) \\
x\_{p} &= (P^{-1}, p)^{-1} x\_{\\mathrm{std}}

N.B. `set_translation_with_origin_shift` computes {math}`(I, p)^{-1} \mathcal{G}_{\mathrm{std}} (I, p)`.
`get_primitive_db_symmetry` computes {math}`(P, 0) (I, p)^{-1} \mathcal{G}_{\mathrm{std}} (I, p) (P, 0)^{-1}` on {math}`(I, p)^{-1} \mathcal{G}_{\mathrm{std}} (I, p)`.

## References

```{bibliography}
:filter: docname in docnames
```
