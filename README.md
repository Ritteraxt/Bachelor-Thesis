# Bachelor-Thesis

The notebooks are not yet in their final form, they work, but still contain "useless" parts of code. 

Flat_Calculation allows to plug in any shape of S(k) = S1(k1)* S2(k2)* S3(K3). 
The notebook with the way too long name allows to pulug in any shape of S(k) = S(k_t). 
Again, the code is currently quite messy and maybe hard to understand. I will fix this up to the 10.07.


The Notebook "AlphaBetaMethod":
If you wish to calculate b_lll with the already precalculated integral-values of Int_G (that is, 2000 sample points in alpha/beta; all l values up to 500, the in bigger steps), then just run the cells from the first one down to cell 8, where Int_T is defined. In Int_T change the vector "Cosarray_Intern" to the shape function that you want to research and then run all the cells below up to cell 13. The calculated values for blll should be in "blllList". Note that the files "l_list.npy" and "IntGvalues.npy" must be in the same folder, if the precalculated values shall be used. If a different sampling in alpha/beta shall be used, one can change the spacing in cell 5. Note that for that case, Int_G must be recalculated for the wished values of l using the very last cell.


The NoteBook "FlatCalculations":
This is the notebook that lets you plug in any SEPARABLE shape function. Just put the shape function that you want to study in the slots S_1,S_2,S_3. Then if you need to you can change the sampling in x (usually that is not necessary, but it will depend on the shape function you look at). This can be done under getx_more. Otherwise just run the cells from up to down. It should be noted that by default the flat shape will be calculated and that in blll_List the NORMALIZED values of blll are stored, that is, they are divided by the "analytical" solution for blll_flat. Also note that if S_1 = s_2 = S_3, then the option "UseSameInts" of FatInt should be activated in order to minimize the runtime. Finally note that currently only every fifth l-value is calculated, but that can be changed without efford.

