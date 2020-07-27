# Multi-PredGO

## This is the readme file that contains the guidelines and information about the compilation of the code of the following paper

**Paper Name:-** A Multi-modal Approach for Protein Function Prediction utilizing Protein Sequence and Structure

 
- **Authors:** Swagarika Jaharlal Giri<sup>1</sup>, Pratik Dutta<sup>1</sup>, Parth Halani<sup>2</sup> and Sriparna Saha<sup>1</sup>
- **Affiliation:** <sup>1</sup>Department of Computer Science and Engineering, IIT Patna, India, <sup>2</sup>Depatment of Computer Science and Engineering, IIIT Guwahati, India
- **Web-server:** http://www1.iitp.ac.in/~pratik.pcs16/multipred.html
- **Status:** Under Minnor Revison in [IEEE Journal of Biomedical and Health Informatics(IEEE JBHI)](https://jbhi.embs.org/)

## Welcome to Multi-PredGO Application:
Multi-PredGO is a multi-modal protein function prediction model that uses the protein sequence, protein structure, and protein-protein interaction network-based information to predict GO-based protein function. As the protein function classes are dependent on each other, we have used a neuro-symbolic hierarchical classification model, which resembles the structure of Gene Ontology (GO), for effectively predicting the dependent protein functions.

## Installation:
```bash
conda create -n multi-predGO python=2.7
source activate multi-predGO
conda install -c bioconda diamond
pip install -r requirements.txt
pip install Flask
pip install -U flask-cors
```

## File Organization
```
|---- data   
|    |--- models 
|         | ---  model_bp.h5      <----- the  best saved model for BP (Multi-predGO)
|         | ---  model_cc.h5      <----- the  best saved model for CC(Multi-predGO)
|         | ---  model_mf.h5      <----- the  best saved model for MF(Multi-predGO)
|         | ---  mode_seq_bp.h5   <----- the  best saved model for Sequential BP
|         | ---  mode_seq_cc.h5   <----- the  best saved model for Sequential CC
|         | ---  mode_seq_mf.h5   <----- the  best saved model for Sequential MF
|
|
|    |---        AccessionNumber_Structure_StatusFileWithAccessionIndex.pkl <-  the file
|                                                         that has the status 
|                                                         of accession no. status 
|              
|    |---        AccessionNumberStatusFileWithAccessionIndex.pkl <- "the file that has the 
|                                                           status of accession no. if the 
|  accession number's sequence , structure and PPIN feature is present in our database or not.
|
|    |---       bp.pkl   <--- The sequence of GO term/ Function sequence (BP)
|    |---       cc.pkl   <--- The sequence of GO term/ Function sequence (CC)
|    |---       mf.pkl   <--- The sequence of GO term/ Function sequence (MF)
|
|    |---       combined-multimodal-bp.pkl   <--- this dataset contains the fasta sequence,
|                   PPIN Knowledge Graph based embedding, and Structural feature information for proteins
|                   participating in biological process.
|
|    |---        combined-multimodal-mf.pkl   <--- this dataset contains the fasta sequence,
|                   PPIN Knowledge Graph based embedding, and Structural feature information for proteins
|                   participating in molecular function. 
|
|    |---       combined-multimodal-bp.pkl   <--- this dataset contains the fasta sequence,
|                  PPIN Knowledge Graph based embedding, and Structural feature information for proteins
|                  participating in biological process.
|    |---         go.obo     <--- gene ontology 
|    |---         go.txt     <--- gene ontology text file
|    |---         interpro.xml <--- file used to make PPI interection network
|
|----  __init__.py  <--- initiate file
|
|----  app.py      <---- the main file that we need to run using command(python app.py)
|                         port configuration and URL.
|----  AUC_ROC_Curve.py
```


## Run the code:
1) To run the code as application: 
Run app.py using command python app.py
app.py will run ur application  in url "http://0.0.0.0:5000/", you can change the host and the part address in app.py
you can get the predictions uisng  http://0.0.0.0:5000/accession?accession_no={accession_no}
example:  http://0.0.0.0:5000/accession?accession_no=P31946, here P31946 is the accession no corresponding which we want a prediction


## Contribution
This work currently is under revision in a peer reviewed journal. For use the code or the preprocessed dataset, please open an issue first to discuss what you would like to do. Also you can contact to the corresponding author [Swagarika Jaharlal Giri (swagarika95@gmail.com)](swagarika95@gmail.com) 



