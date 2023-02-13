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

In order to understand the different skin cancer visual characteristics, an image was built with 3 randomly selected images from each skin cancer presented in the dataset.

<div align="center">
    <img src="/readme_images/mosaic_skin_cancer.png">
</div>

According to the exploration conducted in the dataset's metadata file, the dataset consists of 10015 images and 7 independent variables that provide information about the dataset. There are 57 missing values in the independent variable "Age." To replace these missing values, a study on the distribution of the Age data was conducted and, as a clear symmetrical distribution was visible, the mean Age was used to fill the missing Age values.

<div align="center">
    <img src="/readme_images/age_boxplot.png">
    <img src="/readme_images/age_distplot.png">
</div>

A total data of 7470 patients are recorded in the dataset, were 4001 patients are man, 3419 are woman and 50 patients gender is undisclosed.

<div align="center">
    <img src="/readme_images/gender_plot.png">
</div>

The skin cancer most represented in the dataset is Melanocytic Nevi, labeled **nv**, with 6705 example images. The second most represented are Melanoma, labeled **mel**, with 1113 images, and Benign Keratosis-like Lesions, labeled **bkl**, with 1099 images. Basal Cell Carcinoma, labeled **bcc**, has 514 examples, while Actinic Keratoses and Bowen's Disease, labeled **akiec**, have 327 images. Vascular Lesions, including angiomas, angiokeratomas, pyogenic granulomas, and hemorrhage, labeled **vasc**, and Dermatofibroma, labeled **df**, have significantly fewer example images, with 142 and 115 images respectively.

<div align="center">
    <img src="/readme_images/cancer_plot.png">
</div>

It is possible to observe that 42,6% of the skin cancer recorded are located at the back and in the lower extremity while 25,4% of the cancers are placed at the trunk, upper extremity and abdomen.

<div align="center">
    <img src="/readme_images/cancer_localization_plot.png">
</div>

Only a residual number of cancers was diagnosticated through in-vivo **confocal** microscopy. The second most used method to diagnosis skin cancer was the **follow up** method, which reinforces the importance of regular medical check-ups. The first most used is confirmation by **histopathology** exam.

<div align="center">
    <img src="/readme_images/cancer_diagnosis_types_plot.png">
</div>

It is noteworthy that, although **follow up** is the second most utilized method for diagnosing skin cancer, it was only used to diagnose Melanocytic Nevi. In-vivo **confocal** microscopy diagnosis was only used for the diagnosis of Benign Keratosis-like Lesions. Both Melanocytic Nevi and Benign Keratosis-like Lesions also required medical **consensus** for diagnosis and both required a **histopathology** exam, suggesting that these types of skin cancer may be more challenging to diagnose than the other skin cancers present in the dataset.

<div align="center">
    <img src="/readme_images/each_cancer_diagnosis_types_plot.png">
</div>

The quantity of skin cancer example images by gender is similar but with a slight more number of examples for the masculine gender patients.

<div align="center">
    <img src="/readme_images/cancer_types_prevalence_gender.png">
</div>

It is observed that skin cancer cases are more prevalent in patients aged between 40 and 55 years. There are records of patients with an age of 0, so it is necessary to verify this information.

<div align="center">
    <img src="/readme_images/gender_age_plot.png">
</div>

In the following plot reinforces the idea that at the age of 40 skin cancer diagnosis is higher than in younger ages.
<div align="center">
    <img src="/readme_images/age_cancer_plot.png">
</div>

At the age of 70 more cases of skin cancer located at the face of the patients is more common, while at the age of 50 is more common to diagnosis cancer at the trunk region. The back region is the most prone to skin cancer diagnosis area.

<div align="center">
    <img src="/readme_images/age_cancer_localization_plot.png">
</div>

In men the back region is the are with the most skin cancer cases diagnosed, while in women is the lower extremity area. At the acral region(e.g. peripheral body parts, such as toes and fingers) only women have records of skin cancer diagnosis.

<div align="center">
    <img src="/readme_images/cancer_prevalent_localization_gender.png">
</div>

Melanocytic Nevi is widely distributed in all parts of the body, except for the face area where Benign Keratosis-like Lesions are more common. Melanoma is frequently diagnosed in the back, lower and upper extremities regions.

<div align="center">
    <img src="/readme_images/cancer_prevalent_localization.png">
</div>


The following plot tries to capture in a easier way visual relationships between the different features presented on dataset.
<div align="center">
    <img src="/readme_images/visual_relationships.png">
</div>



## CNN for Human skin cancer images classification
