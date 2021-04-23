# Readme

This file is a reproduction attempt for Alice Wu's paper "Gender Bias in Rumors Among Professionals: An Identity-Based Interpretation." Unfortunately, some files were too large to be exported to this repo; however all the original data can be found on https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/BLEBHI.  

In order to reproduce the paper's 'figure 2' from raw data, these were the steps I took after downloading the folder:
- I downloaded and installed the Anaconda Navigator on my computer (a Mac). I then used it to open and run the python file 'clean_scraped_data.py'. 
- I then opened the file 'clean_raw_text.R' and executed it all in Rstudio. Needless to say, I need to change the directory as appropriate at the top of each file I ran. Some R packages needed to be installed in order for this file to run properly. Any necessary package installations should appear in the Rstudio console. If they don't appear, you can manually install any necessary packages by clicking 'Packages' on the right side of your use interface and selecting which packages you would like to install.
- Using both Rstudio and Anaconda Navigator as appropriate, I then ran the following files in order: 'word_count.py', 'vocab.R', 'prep_for_analysis.py', 'NBER-post-history-ID (by full).R', 'NBER-post-history-ID (by part).R', 'JMC-post-history-ID.R', 'merge_sources.R', 'job-rank.R', and 'gen_full_sample.R'. After running each file, I checked to ensure the appropriate outputs were produced as per the 'README_code' pdf file. If everything has gone as planned up until this point, we have produced the final analysis data from our raw data.
- I ran the 'static_analysis_2019.do' using Stata via the Citrix reciever. This should generate 6 log files and one csv file in the results_static folder, as well as a file named 'figure2_topic_diff.R' in the code folder.
- Run 'figure2_topic_diff.R' in Rstudio. If figure 2 is generated, the reproduction is successful.

The reproduction tree generated by this process (as well as a few additional steps that consisted of running more files) is as follows:
```
  summary_stats_0.log
  └── static_analysis_2019.do
      └── full_sample2019_stata_final.dta
          └── gen_full_sample.R
              ├── full_sample2019.csv
              │   └── merge_sources.R
              │       ├── EJR_ALL_gender_classifiers_2019.csv
              │       │   └── prep_for_analysis.py
              │       │       ├── EJR0_raw_text_cleaned.csv
              │       │       │   └── clean_raw_text.R
              │       │       │       └── EJR0_raw_text.csv
              │       │       │           └── clean_scraped_data.py
              │       │       │               └── scraped_posts.txt
              │       │       ├── counts_Nov2017.npz
              │       │       │   └── word_count.py
              │       │       │       └── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
              │       │       ├── gender_classifiers.csv
              │       │       ├── 0.txt
              │       │       └── all_classifiers_2019.csv
              │       ├── author-history-merged.csv
              │       ├── JMC-history-ID-merged.csv
              │       └── EJR_gender_dataset_Jan2018.csv
              ├── EJR_ALL_categories_2019.csv
              │   └── prep_for_analysis.py
              │       ├── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
              │       ├── counts_Nov2017.npz - CYCLE DETECTED
              │       ├── gender_classifiers.csv
              │       ├── 0.txt
              │       └── all_classifiers_2019.csv
              ├── JMC-history-ID-merged.csv
              ├── author-history-merged.csv
              └── complete-nber-author-info.csv
  summary_stats_1.log
  └── static_analysis_2019.do
      └── full_sample2019_stata_final.dta
          └── gen_full_sample.R
              ├── full_sample2019.csv
              │   └── merge_sources.R
              │       ├── EJR_ALL_gender_classifiers_2019.csv
              │       │   └── prep_for_analysis.py
              │       │       ├── EJR0_raw_text_cleaned.csv
              │       │       │   └── clean_raw_text.R
              │       │       │       └── EJR0_raw_text.csv
              │       │       │           └── clean_scraped_data.py
              │       │       │               └── scraped_posts.txt
              │       │       ├── counts_Nov2017.npz
              │       │       │   └── word_count.py
              │       │       │       └── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
              │       │       ├── gender_classifiers.csv
              │       │       ├── 0.txt
              │       │       └── all_classifiers_2019.csv
              │       ├── author-history-merged.csv
              │       ├── JMC-history-ID-merged.csv
              │       └── EJR_gender_dataset_Jan2018.csv
              ├── EJR_ALL_categories_2019.csv
              │   └── prep_for_analysis.py
              │       ├── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
              │       ├── counts_Nov2017.npz - CYCLE DETECTED
              │       ├── gender_classifiers.csv
              │       ├── 0.txt
              │       └── all_classifiers_2019.csv
              ├── JMC-history-ID-merged.csv
              ├── author-history-merged.csv
              └── complete-nber-author-info.csv
  summary_stats_2.log
  └── static_analysis_2019.do
      └── full_sample2019_stata_final.dta
          └── gen_full_sample.R
              ├── full_sample2019.csv
              │   └── merge_sources.R
              │       ├── EJR_ALL_gender_classifiers_2019.csv
              │       │   └── prep_for_analysis.py
              │       │       ├── EJR0_raw_text_cleaned.csv
              │       │       │   └── clean_raw_text.R
              │       │       │       └── EJR0_raw_text.csv
              │       │       │           └── clean_scraped_data.py
              │       │       │               └── scraped_posts.txt
              │       │       ├── counts_Nov2017.npz
              │       │       │   └── word_count.py
              │       │       │       └── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
              │       │       ├── gender_classifiers.csv
              │       │       ├── 0.txt
              │       │       └── all_classifiers_2019.csv
              │       ├── author-history-merged.csv
              │       ├── JMC-history-ID-merged.csv
              │       └── EJR_gender_dataset_Jan2018.csv
              ├── EJR_ALL_categories_2019.csv
              │   └── prep_for_analysis.py
              │       ├── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
              │       ├── counts_Nov2017.npz - CYCLE DETECTED
              │       ├── gender_classifiers.csv
              │       ├── 0.txt
              │       └── all_classifiers_2019.csv
              ├── JMC-history-ID-merged.csv
              ├── author-history-merged.csv
              └── complete-nber-author-info.csv
  summary_stats_3.log
  └── static_analysis_2019.do
      └── full_sample2019_stata_final.dta
          └── gen_full_sample.R
              ├── full_sample2019.csv
              │   └── merge_sources.R
              │       ├── EJR_ALL_gender_classifiers_2019.csv
              │       │   └── prep_for_analysis.py
              │       │       ├── EJR0_raw_text_cleaned.csv
              │       │       │   └── clean_raw_text.R
              │       │       │       └── EJR0_raw_text.csv
              │       │       │           └── clean_scraped_data.py
              │       │       │               └── scraped_posts.txt
              │       │       ├── counts_Nov2017.npz
              │       │       │   └── word_count.py
              │       │       │       └── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
              │       │       ├── gender_classifiers.csv
              │       │       ├── 0.txt
              │       │       └── all_classifiers_2019.csv
              │       ├── author-history-merged.csv
              │       ├── JMC-history-ID-merged.csv
              │       └── EJR_gender_dataset_Jan2018.csv
              ├── EJR_ALL_categories_2019.csv
              │   └── prep_for_analysis.py
              │       ├── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
              │       ├── counts_Nov2017.npz - CYCLE DETECTED
              │       ├── gender_classifiers.csv
              │       ├── 0.txt
              │       └── all_classifiers_2019.csv
              ├── JMC-history-ID-merged.csv
              ├── author-history-merged.csv
              └── complete-nber-author-info.csv
  summary_stats_4.log
  └── static_analysis_2019.do
      └── full_sample2019_stata_final.dta
          └── gen_full_sample.R
              ├── full_sample2019.csv
              │   └── merge_sources.R
              │       ├── EJR_ALL_gender_classifiers_2019.csv
              │       │   └── prep_for_analysis.py
              │       │       ├── EJR0_raw_text_cleaned.csv
              │       │       │   └── clean_raw_text.R
              │       │       │       └── EJR0_raw_text.csv
              │       │       │           └── clean_scraped_data.py
              │       │       │               └── scraped_posts.txt
              │       │       ├── counts_Nov2017.npz
              │       │       │   └── word_count.py
              │       │       │       └── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
              │       │       ├── gender_classifiers.csv
              │       │       ├── 0.txt
              │       │       └── all_classifiers_2019.csv
              │       ├── author-history-merged.csv
              │       ├── JMC-history-ID-merged.csv
              │       └── EJR_gender_dataset_Jan2018.csv
              ├── EJR_ALL_categories_2019.csv
              │   └── prep_for_analysis.py
              │       ├── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
              │       ├── counts_Nov2017.npz - CYCLE DETECTED
              │       ├── gender_classifiers.csv
              │       ├── 0.txt
              │       └── all_classifiers_2019.csv
              ├── JMC-history-ID-merged.csv
              ├── author-history-merged.csv
              └── complete-nber-author-info.csv
  codebook_dta.log
  └── static_analysis_2019.do
      └── full_sample2019_stata_final.dta
          └── gen_full_sample.R
              ├── full_sample2019.csv
              │   └── merge_sources.R
              │       ├── EJR_ALL_gender_classifiers_2019.csv
              │       │   └── prep_for_analysis.py
              │       │       ├── EJR0_raw_text_cleaned.csv
              │       │       │   └── clean_raw_text.R
              │       │       │       └── EJR0_raw_text.csv
              │       │       │           └── clean_scraped_data.py
              │       │       │               └── scraped_posts.txt
              │       │       ├── counts_Nov2017.npz
              │       │       │   └── word_count.py
              │       │       │       └── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
              │       │       ├── gender_classifiers.csv
              │       │       ├── 0.txt
              │       │       └── all_classifiers_2019.csv
              │       ├── author-history-merged.csv
              │       ├── JMC-history-ID-merged.csv
              │       └── EJR_gender_dataset_Jan2018.csv
              ├── EJR_ALL_categories_2019.csv
              │   └── prep_for_analysis.py
              │       ├── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
              │       ├── counts_Nov2017.npz - CYCLE DETECTED
              │       ├── gender_classifiers.csv
              │       ├── 0.txt
              │       └── all_classifiers_2019.csv
              ├── JMC-history-ID-merged.csv
              ├── author-history-merged.csv
              └── complete-nber-author-info.csv
  'Figure 2'
  └── figure2_topic_diff.R
      └── topic-diff-by-month.csv
          └── static_analysis_2019.do
              └── full_sample2019_stata_final.dta
                  └── gen_full_sample.R
                      ├── full_sample2019.csv
                      │   └── merge_sources.R
                      │       ├── EJR_ALL_gender_classifiers_2019.csv
                      │       │   └── prep_for_analysis.py
                      │       │       ├── EJR0_raw_text_cleaned.csv
                      │       │       │   └── clean_raw_text.R
                      │       │       │       └── EJR0_raw_text.csv
                      │       │       │           └── clean_scraped_data.py
                      │       │       │               └── scraped_posts.txt
                      │       │       ├── counts_Nov2017.npz
                      │       │       │   └── word_count.py
                      │       │       │       └── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
                      │       │       ├── gender_classifiers.csv
                      │       │       ├── 0.txt
                      │       │       └── all_classifiers_2019.csv
                      │       ├── author-history-merged.csv
                      │       ├── JMC-history-ID-merged.csv
                      │       └── EJR_gender_dataset_Jan2018.csv
                      ├── EJR_ALL_categories_2019.csv
                      │   └── prep_for_analysis.py
                      │       ├── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
                      │       ├── counts_Nov2017.npz - CYCLE DETECTED
                      │       ├── gender_classifiers.csv
                      │       ├── 0.txt
                      │       └── all_classifiers_2019.csv
                      ├── JMC-history-ID-merged.csv
                      ├── author-history-merged.csv
                      └── complete-nber-author-info.csv
  mlogit-full-after-Aug2017.log
  └── dynamic_analysis_2019.do
      └── full_sample2019_stata_final.dta
          └── gen_full_sample.R
              ├── full_sample2019.csv
              │   └── merge_sources.R
              │       ├── EJR_ALL_gender_classifiers_2019.csv
              │       │   └── prep_for_analysis.py
              │       │       ├── EJR0_raw_text_cleaned.csv
              │       │       │   └── clean_raw_text.R
              │       │       │       └── EJR0_raw_text.csv
              │       │       │           └── clean_scraped_data.py
              │       │       │               └── scraped_posts.txt
              │       │       ├── counts_Nov2017.npz
              │       │       │   └── word_count.py
              │       │       │       └── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
              │       │       ├── gender_classifiers.csv
              │       │       ├── 0.txt
              │       │       └── all_classifiers_2019.csv
              │       ├── author-history-merged.csv
              │       ├── JMC-history-ID-merged.csv
              │       └── EJR_gender_dataset_Jan2018.csv
              ├── EJR_ALL_categories_2019.csv
              │   └── prep_for_analysis.py
              │       ├── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
              │       ├── counts_Nov2017.npz - CYCLE DETECTED
              │       ├── gender_classifiers.csv
              │       ├── 0.txt
              │       └── all_classifiers_2019.csv
              ├── JMC-history-ID-merged.csv
              ├── author-history-merged.csv
              └── complete-nber-author-info.csv
  mlogit-full-before-Aug2017.log
  └── dynamic_analysis_2019.do
      └── full_sample2019_stata_final.dta
          └── gen_full_sample.R
              ├── full_sample2019.csv
              │   └── merge_sources.R
              │       ├── EJR_ALL_gender_classifiers_2019.csv
              │       │   └── prep_for_analysis.py
              │       │       ├── EJR0_raw_text_cleaned.csv
              │       │       │   └── clean_raw_text.R
              │       │       │       └── EJR0_raw_text.csv
              │       │       │           └── clean_scraped_data.py
              │       │       │               └── scraped_posts.txt
              │       │       ├── counts_Nov2017.npz
              │       │       │   └── word_count.py
              │       │       │       └── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
              │       │       ├── gender_classifiers.csv
              │       │       ├── 0.txt
              │       │       └── all_classifiers_2019.csv
              │       ├── author-history-merged.csv
              │       ├── JMC-history-ID-merged.csv
              │       └── EJR_gender_dataset_Jan2018.csv
              ├── EJR_ALL_categories_2019.csv
              │   └── prep_for_analysis.py
              │       ├── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
              │       ├── counts_Nov2017.npz - CYCLE DETECTED
              │       ├── gender_classifiers.csv
              │       ├── 0.txt
              │       └── all_classifiers_2019.csv
              ├── JMC-history-ID-merged.csv
              ├── author-history-merged.csv
              └── complete-nber-author-info.csv
  vocab_Nov2017.pkl
  └── word_count.py
      └── EJR0_raw_text_cleaned.csv
          └── clean_raw_text.R
              └── EJR0_raw_text.csv
                  └── clean_scraped_data.py
                      └── scraped_posts.txt
  The folder gender_bias__economics/data/vocab/category
  └── vocab.R
      └── cleaned_vocab.csv
  author-history-ID-by-part.csv
  └── NBER-post-history-ID (by part).R
      ├── EJR0_raw_text_cleaned.csv
      │   └── clean_raw_text.R
      │       └── EJR0_raw_text.csv
      │           └── clean_scraped_data.py
      │               └── scraped_posts.txt
      ├── author-history-ID-by-full.csv
      │   └── NBER-post-history-ID (by full).R
      │       ├── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
      │       └── nber-author-info.csv
      └── nber-ejr-author-info.csv
  JMC-history-ID.csv
  └── JMC-post-history-ID.R
      ├── EJR0_raw_text_cleaned.csv
      │   └── clean_raw_text.R
      │       └── EJR0_raw_text.csv
      │           └── clean_scraped_data.py
      │               └── scraped_posts.txt
      └── jmc_data_gender_nonmissing.csv
  full_sample_job_rank.csv
  └── job-rank.R
      └── full_sample2019.csv
          └── merge_sources.R
              ├── EJR_ALL_gender_classifiers_2019.csv
              │   └── prep_for_analysis.py
              │       ├── EJR0_raw_text_cleaned.csv
              │       │   └── clean_raw_text.R
              │       │       └── EJR0_raw_text.csv
              │       │           └── clean_scraped_data.py
              │       │               └── scraped_posts.txt
              │       ├── counts_Nov2017.npz
              │       │   └── word_count.py
              │       │       └── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
              │       ├── gender_classifiers.csv
              │       ├── 0.txt
              │       └── all_classifiers_2019.csv
              ├── author-history-merged.csv
              ├── JMC-history-ID-merged.csv
              └── EJR_gender_dataset_Jan2018.csv
  full_sample2019_stata.csv
  └── gen_full_sample.R
      ├── full_sample2019.csv
      │   └── merge_sources.R
      │       ├── EJR_ALL_gender_classifiers_2019.csv
      │       │   └── prep_for_analysis.py
      │       │       ├── EJR0_raw_text_cleaned.csv
      │       │       │   └── clean_raw_text.R
      │       │       │       └── EJR0_raw_text.csv
      │       │       │           └── clean_scraped_data.py
      │       │       │               └── scraped_posts.txt
      │       │       ├── counts_Nov2017.npz
      │       │       │   └── word_count.py
      │       │       │       └── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
      │       │       ├── gender_classifiers.csv
      │       │       ├── 0.txt
      │       │       └── all_classifiers_2019.csv
      │       ├── author-history-merged.csv
      │       ├── JMC-history-ID-merged.csv
      │       └── EJR_gender_dataset_Jan2018.csv
      ├── EJR_ALL_categories_2019.csv
      │   └── prep_for_analysis.py
      │       ├── EJR0_raw_text_cleaned.csv - CYCLE DETECTED
      │       ├── counts_Nov2017.npz - CYCLE DETECTED
      │       ├── gender_classifiers.csv
      │       ├── 0.txt
      │       └── all_classifiers_2019.csv
      ├── JMC-history-ID-merged.csv
      ├── author-history-merged.csv
      └── complete-nber-author-info.csv
```