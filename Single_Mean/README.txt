Documentation of Single_Mean.py file

This model was thought to be used for only one cell type. And consider 
only active genes to visualize different analysis levels.

There are two parts of functions. The first part of the functions is partial
functions that will be embedded in the final functions. Those are defined in
the second part.

##############################################################################
The first part of the defined functions is:

1. read_expression_data(direction)
Read in expression data files .JSON generated by pipeline.

2. read_mov_data(direction)
Read in movement data files .JSON generated by pipeline.

3. active_genes(direction)
Sort out the list of active genes and also the gene expression DataFrame only 
containing them. 

4. PCA_tool(DataFrame, delete_column)
Applying PCA approach to get principal components and information content.

5. PCA_plot(conditions, info_content, plot_name, principalDf)
Visualization of PCA results for both mean expression DataFrames and mean
EWFD score DataFrame.

##############################################################################
The second part of the defined functions is:

1. active_gene_mean(direction)
Apply only active genes with PCA to represent mean values of gene expressions. 
A panel image of PCA results will be returned. 

2. active_transcript_mean(direction)
With the PCA representing mean values of transcript expressions only for 
active genes. 
A panel image of PCA results will be returned. 

3. active_rel_transcript_mean(direction)
With the PCA representing mean values of relative transcript expressions 
only for active genes. 
A panel image of PCA results will be returned. 

4. active_ewfd_mean(mov_direction, expr_direction)
With the PCA representing mean values of EWFD scores only for active genes. 
The EWFD scores are calculated with movements.
A panel image of PCA results will be returned. 

##############################################################################
##############################################################################

Documentation of PC_Single_Mean.py file

This model was thought to be used for only one cell type and only for active
genes (i.e., non-zero gene expression in all replicates).

There are three parts of function definitions. The first part defines the
partial functions that will be applied to the functions in the second part.
The function in the last part applies the functions from the second part.

##############################################################################
The first part of functions:

1. read_expression_data(direction)
Read in expression data files .JSON generated by pipeline.

2. read_mov_data(direction)
Read in movement data files .JSON generated by pipeline.

3. find_active_genes(direction)
Generate a list of active genes based on the gene expressions.

4. PCA_tool(DataFrame, delete_column, conditions)
Apply PCA methond on the given DataFrame. Returns the overall information 
content and all principal components for each data point.

##############################################################################
The second part of functions:

1.  PC_gene_expr(direction)
Generate a dictionary containing overall information content vector and all 
principal components from PCA applied on mean gene expression values.

2. PC_transcript_expr(direction)
Generate a dictionary containing overall information content vector and all 
principal components from PCA applied on mean transcript expression values.

3. PC_rel_transcript_expr(direction)
Generate a dictionary containing overall information content vector and all 
principal components from PCA applied on mean relative transcript expression 
values.

4. PC_EWFD(mov_direction, expr_direction)
Generate a dictionary containing overall information content vector and all 
principal components from PCA applied on mean EWFD scores.

##############################################################################
The third part of functions:

1.  write_JSON(expr_direction, mov_direction, writepath)
Summarizing the PCA information for gene expression, transcript expression,
relative transcript expression and EWFD score into a .JSON file. 
