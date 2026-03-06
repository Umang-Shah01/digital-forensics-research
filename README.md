# Digital Forensics vs. Anti-Forensics: An Empirical Data Recovery Evaluation

This repository hosts the portfolio and findings of an empirical evaluation of five open-source digital forensic tools tested against varying anti-forensic deletion techniques[cite: 10, 20]. [cite_start]The research was originally conducted as a master's dissertation for the NCSC-certified MSc in Computer Science for Cyber Security programme at Heriot-Watt University[cite: 5, 6, 237].

🔗 **[View the Interactive Portfolio](https://[yourusername].github.io/[your-repo-name]/)** *(Replace with your live GitHub Pages link)*

## 📌 Executive Summary

The proliferation of anti-forensic tools has significantly impaired the ability of investigators to recover evidential data[cite: 10]. [cite_start]This project systematically evaluated open-source recovery tools across different storage media to determine their effectiveness against standard deletion, disk formatting, and secure cryptographic-grade file wiping[cite: 10, 20]. 

Crucially, the findings carry direct regulatory implications for organizations subject to the European Union's GDPR Article 17 (Right to Erasure) and India's Digital Personal Data Protection (DPDP) Act 2023[cite: 10, 15, 16].

## ⚖️ Regulatory & Business Impact (GRC)

Data controllers and fiduciaries face a critical compliance ambiguity: which deletion methods are sufficient, and which are forensically reversible[cite: 17]? This research provides technical, empirical answers:
**Standard deletion and formatting are non-compliant:** These methods permit substantial data recovery (up to 100%) and do not satisfy the threshold of "effective erasure"[cite: 10, 157, 164].
**Verifiable Erasure Established:** DOD 5220.22M three-pass overwriting renders all meaningful file content unrecoverable across the tested tools, serving as a minimum technical standard for legal compliance[cite: 10, 212, 214].
**Indian Market Relevance:** This study connects forensic tool evaluation results directly to DPDP Act 2023 Section 8(7) technical compliance requirements[cite: 172, 177].

## 🔬 Experimental Methodology

The experiments were designed to mirror real-world forensic investigations and were conducted strictly under the Association of Chief Police Officers (ACPO) Good Practice Guidelines for Digital Evidence[cite: 10, 20, 55]. 
***Storage Media:** USB Drive (exFAT), SD Card (exFAT), HDD partition (NTFS), and Virtual Hard Disk (FAT)[cite: 10, 63].
**Dataset:** A controlled dataset of 520 files spanning 8 common categories (Archives, Audio, Documents, Executables, Images, Text, Videos, Folders)[cite: 57, 58].
**Anti-Forensic Techniques:** Standard Deletion (Delete/Shift+Delete), Windows Formatting, and DOD 5220.22M (3-pass overwriting)[cite: 10].
**Evidence Integrity:** Full chain-of-custody documentation, write-blocking of source media, and forensic imaging (.E01, .img) prior to analysis[cite: 10, 55, 83, 84].

## 🛠️ Digital Forensic Tools Evaluated

The tools were validated against National Institute of Standards and Technology (NIST) Computer Forensics Tool Testing (CFTT) functional requirements[cite: 54, 73]:
1. **Recuva:** Highest overall average recovery rate (72.9%) and strongest performer on formatting cases[cite: 113, 133].
2. **Autopsy:** Highly effective across varied scenarios (70.9% average recovery)[cite: 133, 141]. 
3. **QPhotoRec:** An underutilized GUI tool with particular strength in NTFS formatting scenarios[cite: 209].
4. **FTK Imager:** Highly effective for simple deletion cases but fails systematically (0% recovery) on formatted media due to its reliance on file signature indexes[cite: 111, 112, 208].
5. **Foremost:** The weakest performer (37.4% average) due to its limited file-type signature support[cite: 133, 210].

## 🚀 Key Technical Findings

**DOD 5220.22M Defeats Open-Source Tools:** Three-pass overwriting produced zero meaningful file content recovery across all five tools and all four media types[cite: 119]. 
**Partial Recovery Holds Value:** While DOD 5220.22M destroyed the content, tools like Autopsy, FTK Imager, and Recuva detected "residual artefacts" (0-byte file entries and system infrastructure files), which confirms prior file existence and can establish investigative intent[cite: 122, 127].
**VHD & 4K Alignment:** The FAT file system's simpler structure combined with VHD 4K alignment contributed to superior recovery outcomes (100% for Autopsy and Recuva) during formatting cases[cite: 116, 117].

## 👨‍💻 About the Author

**Umang Shah** *MSc Computer Science for Cyber Security* | [cite_start]*Heriot-Watt University* [cite: 5, 6]
Connect with me on [LinkedIn](https://linkedin.com/in/umangshah) or view my full [Portfolio](https://umangshah.dev).
