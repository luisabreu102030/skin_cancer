# Skin cancer images classification


<div align="center">
    <img src="/readme_images/checking_skin_cancer.jpg">
</div>

## Skin cancer 

Skin cancer is the most common cancer in the United States of America (U.S.A.), and is estimated that about 4.9 million U.S. adults were treated for skin cancer each year from 2007 to 2011, for an average annual treatment cost of $8.1 billion. [1](https://pubmed.ncbi.nlm.nih.gov/26042651/),[2](https://pubmed.ncbi.nlm.nih.gov/25442229/)

It is estimated that approximately 9500 people are diagnosed with skin cancer every day, and that one in five Americans will develop skin cancer in their lifetime. [3](https://pubmed.ncbi.nlm.nih.gov/25928283/),[4](https://acsjournals.onlinelibrary.wiley.com/doi/10.3322/caac.21708),[5](https://pubmed.ncbi.nlm.nih.gov/20231498/)

Skin cancer is the out-of-control growth of abnormal cells in the epidermis, the outermost skin layer, caused by unrepaired DNA damage that triggers mutations. These mutations lead the skin cells to multiply rapidly and form malignant tumors. The main types of skin cancer are basal cell carcinoma, squamous cell carcinoma, melanoma and Merkel cell carcinoma. [6](https://www.skincancer.org/skin-cancer-information/)

The main causes of skin cancer are the excess exposure to UV radiation from sunlight and the use of indoor UV tanning beds. Genetic predisposition is also a factor that increases the probability of skin cancer. [5](https://pubmed.ncbi.nlm.nih.gov/20231498/)

If found early, skin cancer is highly treatable. Often a dermatologist can treat an early skin cancer by simply removing the cancer, but late found cancers becomes more difficult to treat. [7](https://www.aad.org/public/diseases/skin-cancer/find/know-how) 

Dermatologists advises a regular self exam with a monthly periodicity. During each exam one should look for warning signs like changes in size, shape, or color of a mole or other skin lesion, the appearance of a new growth on the skin, or a sore that doesn't heal. If one notice any spots on the skin that are different from the others, or anything changing, itching or bleeding one should contact a dermatologist as soon as possible. [7](https://www.aad.org/public/diseases/skin-cancer/find/know-how)


## Dataset description

The HAM10000 ("Human Against Machine with 10000 training images") dataset was provided by International Skin Imaging Collaboration (ISIC) for the 2018 challenge hosted at the Medical Image Computing and Computer Assisted Intervention (MICCAI) conference in Granada, Spain and is a collection of dermatoscopic images from different populations, acquired and stored by different modalities. The dataset consists of 10015 dermatoscopic images, and corresponding metadata, which can serve as a training set for academic machine learning purposes. [dataset](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/DBW86T)

HAM10000 dataset has **7 different classes** of skin cancer which are listed below :
- Actinic keratoses and intraepithelial carcinoma / Bowen's disease (**akiec**), 
- Basal cell carcinoma (**bcc**), 
- Benign keratosis-like lesions (solar lentigines / seborrheic keratoses and lichen-planus like keratoses, **bkl**),
- Dermatofibroma (**df**),
- Melanoma (**mel**), 
- Melanocytic nevi (**nv**) 
- Vascular lesions (angiomas, angiokeratomas, pyogenic granulomas and hemorrhage, **vasc**)

HAM10000 dataset metadata has **7 different features** which are listed below :

<ol>
  <li><strong>lesion_id</strong> : patient lesion id, one lesion can have multiple images</li>
  <li><strong>image_id</strong> : image id, each image is unique</li>
  <li><strong>dx</strong> : skin cancer class [akiec, bcc, bkl, df, mel, nv, vasc]</li>
  <li><strong>dx_type</strong> : how the diagnosis was achieved [histo, follow_up, consensus, confocal]</li>
    <ul>
      <li><ins>histo</ins> : confirmed through histopathology </li>
      <li><ins>follow_up</ins> : diagnosis through follow-up examination</li>
      <li><ins>consensus</ins> : expert consensus</li>
      <li><ins>confocal</ins> : in-vivo confocal microscopy</li>
    </ul>
  <li><strong>age</strong> : patient age</li>
  <li><strong>sex</strong> : patient gender</li>
  <li><strong>localization</strong> : cancer localization</li>
</ol>


## Data exploration

## CNN for Human skin cancer images classification
