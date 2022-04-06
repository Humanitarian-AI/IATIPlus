### IATI Data on Dropbox
![Organization Data Folders](https://github.com/Humanitarian-AI/IATI-Firestore/blob/master/Media/IATI_Org_Folders.png)

A daily snapshot of all IATI data is stored on Dropbox and IATI updates the corpus every 24 hours. The data is stored in hundreds of individuals folders organized by publishing organizations. Information on accessing the data is located [here](https://github.com/codeforIATI/iati-data-dump).

The [Dropbox Extractor](https://github.com/Humanitarian-AI/IATI-Extractor) will systematically extract XML data stored in organization folders and export the data to the Google Cloud Firestore database.
