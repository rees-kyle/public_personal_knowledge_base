---
id: hnj9noxue12k1ujp8i988l2
title: '14'
desc: ''
updated: 1689301742004
created: 1689301615695
---

1. [x] add azure code exp date to calander
1. [x] blur certificate number
    1. [x] remove commit from history
        1. [x] git pull
        1. [x] git filter-branch --force --index-filter "git rm --cached --ignore-unmatch ./file/path/file.ext" --prune-empty --tag-name-filter cat -- --all
        1. [x] echo "file/path/file.ext" >> .gitignore
        1. [x] git push origin --force --all
        1. [x] git push origin --force --tags
 
    ```mermaid
    graph TD;
    portfolio-->certificates
    ```
    1. [x] add original certificate to private_personal_knowledge_base
        1. [x] move scrum_developer_training.pdf from downloads to private_personal_knowledge_base\notes\assests\certificates
        1. [x] add portfolio.certificates.md
        1. [x] modify certificates (link certificate)
    1. [x] Add redacted certificate to public_personal_knowledge_base and move scrum_developer_training.pdf from private_personal_knowledge_base\notes\assests\certificates to public_personal_knowledge_base\notes\assests\certificates
        1. [x] move file
            1. [x] copy 
            1. [x] paste 
        1. [x] rename as scrum_developer_training_redacted.pdf
        1. [x] install libre office
        1. [x] edit certificate
            1. [x] redact
            1. [x] save 
        1. [x] modify certificates.md
1. [x] modify git-bash.guide.md
    ## Remove File from Git History
    - git pull
    - git filter-branch --force --index-filter "git rm --cached --ignore-unmatch ./file/path/file.ext" --prune-empty --tag-name-filter cat -- --all
    - echo "file/path/file.ext" >> .gitignore
    - git push origin --force --all
    - git push origin --force --tags
1. [x] modify dendron.guide.md
1. [x] research techniques on documenting code
    1. [x] jupyter notebooks