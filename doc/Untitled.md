{\rtf1\ansi\ansicpg1252\cocoartf1504\cocoasubrtf830
{\fonttbl\f0\fnil\fcharset0 Menlo-Regular;}
{\colortbl;\red255\green255\blue255;\red38\green38\blue38;\red242\green242\blue242;}
{\*\expandedcolortbl;;\cssrgb\c20000\c20000\c20000;\cssrgb\c96078\c96078\c96078;}
\paperw11900\paperh16840\margl1440\margr1440\vieww10800\viewh8400\viewkind0
\deftab720
\pard\pardeftab720\sl360\partightenfactor0

\f0\fs26 \cf2 \cb3 \expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 #\
# Final results\
\
# jSON format structure\
\
This is the desired Json format after QC and Phenomization for use in the Simulation process.\
\
**submitter\{\}**\
\
\{user\\_email, user\\_name, user\\_team\}\
\
**documents[]**\
\
[\{document\\_name,is\\_vcf\}]\
\
&gt;&gt; Additional information on the case, which might be provided by the user.\
\
&gt;&gt; Can be a provided vcf  file.\
\
**geneList**\
\
     [has\\_mask, feature\\_score, gene\\_symbol, combined\\_score, syndrome\\_name,  gestalt\\_score, gene\\_id, gene\\_omim\\_id]\
\
     &gt;&gt; gene information added after mapping gene to syndromes\
\
     &gt;&gt; Can contain extra information from  Simulation step : [cadd\\_phred\\_score, pheno\\_score, boqa\\_score, cadd\\_raw\\_score]\
\
**selected\\_syndromes**\
\
[has\\_mask, omim\\_id, syndrome\\_name]\
\
&gt;&gt;Syndrome as selected by the user in the Face2Gene interface.\
\
**detected\\_syndromes**\
\
[combined\\_score, feature\\_score, gestalt\\_score, has\\_mask, omim\\_id:|[], syndrome\\_name]\
\
&gt;&gt; Syndromes detected by the Face2Gene algorithm based on the provided phenotypic information as specified in features and the provided image.\
\
**features[]**\
\
&gt;&gt; List of phenotypic features specified using HPO terminology.\
\
**ranks []**\
\
[\{feature\\_score, value\\_pheno, disease-name\\_pheno,omim\\_id, combined\\_score , value\\_boqa, disease-name\\_boqa, syndrome\\_name , gene-id , gestalt\\_score , confirmed ,  gene-symbol\}]\
\
&gt;&gt; Ranks generated after Phenomization\
\
**algo\\_deploy\\_version**\
\
     Algorithm version used in the generation of the jSON File. This might affect the detected syndromes and masks. This might change if the dumps are updated for single cases.\
\
**case\\_id**\
\
Unique id identifying the case on Face2Gene.\
\
**vcf []**\
\
Name of Vcf file when available\
\
**processing []**\
\
List of the scripts used to produce output file and background\\_sample\
\
**genomic\\_entries []**\
\
[&lt;entry\\_filename&gt;]\
\
References the filename of the genomic entry for the case. There might be more than one genomic entry per case.\
\
**genomicData[]**\
\
[ Mutations \{result, Build, HGVS-code, additional info, Inheritance Mode\}\
\
, Test Information \{Gene Name, Genotype, Notation, Mutation Type, Molecular Test\}\
\
&gt;&gt; information extracted from genomic\\_entries in preprocessing step\
}