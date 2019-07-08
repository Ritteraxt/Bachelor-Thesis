# Bachelor-Thesis

Four main notebooks:
"AlphaBetaMethod" implemented the Alpha-Beta-Method to calculate the Bispectrum.
"FlatCalculations" implemented the separable approach.
"Tetrahedron_analysis_Meshgrid" calculates the analytical form of the Bessel integral; either for individual points or for a whole tetrahedron-cut-through.
"Plot_The_Triangle" is a routine to plot the tetrahedron cutthroughs.


The Notebook "AlphaBetaMethod":
If you wish to calculate b_lll with the already precalculated integral-values of Int_G (that is, 2000 sample points in alpha/beta; all l values up to 500, the in bigger steps), then just run the cells from the first one down to cell 8, where Int_T is defined. In Int_T change the vector "Cosarray_Intern" to the shape function that you want to research and then run all the cells below up to cell 13. The calculated values for blll should be in "blllList". Note that the files "l_list.npy" and "IntGvalues.npy" must be in the same folder, if the precalculated values shall be used. If a different sampling in alpha/beta shall be used, one can change the spacing in cell 5. Note that for that case, Int_G must be recalculated for the wished values of l using the very last cell.


The Notebook "FlatCalculations":
This is the notebook that lets you plug in any SEPARABLE shape function. Just put the shape function that you want to study in the slots S_1,S_2,S_3. Then if you need to you can change the sampling in x (usually that is not necessary, but it will depend on the shape function you look at). This can be done under getx_more. Otherwise just run the cells from up to down. It should be noted that by default the flat shape will be calculated and that in blll_List the NORMALIZED values of blll are stored, that is, they are divided by the "analytical" solution for blll_flat. Also note that if S_1 = s_2 = S_3, then the option "UseSameInts" of FatInt should be activated in order to minimize the runtime. Finally note that currently only every fifth l-value is calculated, but that can be changed without efford.

The Notebook "Tetrahedron_analysis_Meshgrid":
This notebook calculates the Bessel integral in analytical form. In principle, on can just calculate the data of an individual combination of k1,k2,k3 and l1,l2,l3 with the "J_Modified" function. If you wish to plot a cut-through though a tetrahedron for a given combination of l, then use the function "Int_G_Meshgrid" instead. This will calculate the alpha-beta plane for the sampling that can be manually set when calculating "AlphaArray" and "BetaArray". Note that this cut-through can only be plotted with the Plotroutine "Plot_The_triangle" (different notebook), if alpha_initial and beta_initial have the same number of points. Finally, if the data is generated, save it to a .npy file with the prefix "DataDreieckMashgrid", so that the plot routine works. I know that that is surely not the most beautiful solution, but the time schedule is tight and it works.


The Notebook "Plot_The_Triangle":
This is a very limited plotting routine. It will only accept data in the form that is mentioned above, i.e. there must be a file with the prefix "DataDreieckMashgrid" in the filename. The data must be the integral values in the form of the meshgrid. The plot can be done logarithmically or normal; the layout can be changed. Also, if the l´s have a symmetryline in l1, one is allowed to calculate only HALF the triangle, so with alpha going from 0 to 1 with HALF as many points. Probably this plot routine is not too helpful.



