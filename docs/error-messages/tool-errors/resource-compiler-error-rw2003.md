---
title: "Erreur RW2003 du compilateur de ressources  | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RW2003"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW2003"
ms.assetid: 9dc0ba70-6776-4aef-b316-5f1711d8e42e
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur RW2003 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erreur de génération  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  **Erreur : le fichier de ressources du fichier bitmap n'est pas au format 3.00**  
  
     Il n'est pas possible d'utiliser des bitmaps créées dans Windows version 2.x dans des fichiers de ressources de la version 3.x.  Vous devez les recréer ou les convertir au format 3.x.  
  
2.  **Erreur : bitmap indépendante du périphérique \(DIB\) obsolète dans le nom de ressource.  Passez\-la à SDKPAINT**  
  
     Une bitmap indépendante du périphérique \(DIB, Device Independent Bitmap\) de la ressource spécifiée est incompatible avec le format Windows 3.0.  Vous devez la recréer ou la convertir au format 3.x.  
  
3.  **Erreur : le nom de ressource du fichier de ressources n'est pas au format 3.00**  
  
     Une icône ou un curseur de la ressource spécifiée a été créé dans une version antérieure de Windows.  Vous devez recréer ou convertir l'icône ou le curseur au format 3.x.  
  
4.  **Format de l'en\-tête de la bitmap indépendante du périphérique inconnu**  
  
     L'en\-tête de bitmap n'est pas une structure BITMAPCOREHEADER ou BITMAPINFOHEADER.  
  
5.  **Impossible d'initialiser les informations de symbole**  
  
     Cette erreur se produit uniquement dans Visual C\+\+.  Vous avez probablement trop de fichiers ouverts ou vous ne pouvez pas ouvrir ou écrire les fichiers de données requis par Visual C\+\+ pour importer les symboles de votre script.  Visual C\+\+ tente de créer ces fichiers dans le répertoire spécifié dans la variable d'environnement **TMP**, ou dans le répertoire en cours, si aucun autre répertoire n'est spécifié.  
  
6.  **Impossible d'enregistrer les informations de symbole**  
  
     Cette erreur se produit uniquement dans Visual C\+\+.  Vous avez probablement trop de fichiers ouverts ou vous ne pouvez pas fermer les fichiers de données requis par Visual C\+\+ pour l'importation des symboles de votre script, ou écrire dans ces derniers.  Visual C\+\+ tente d'utiliser les fichiers dans le répertoire spécifié dans la variable d'environnement **TMP**, ou dans le répertoire en cours, si aucun autre répertoire n'est spécifié.  
  
7.  **Le fichier de ressources du fichier bitmap n'est pas au format 2.03**  
  
     Une image bitmap a été créée dans une version antérieure à la version 2.03.  Vous devez la convertir ou la recréer en utilisant le format de la version 3.00 ou ultérieure.  
  
8.  **Ressources trop volumineuses**  
  
     Dans Windows 3.1, un fichier de ressources ne doit pas dépasser 65 000 octets environ.  Si votre fichier de ressources dépasse cette limite, vous ne serez pas en mesure de le compiler à l'aide de Visual C\+\+, ni à l'aide du compilateur de ressources de ligne de commande.  Cette restriction ne s'applique pas aux curseurs, icônes, bitmaps ou autres ressources basées sur des fichiers.  
  
9. **Le fichier de ressources n'est pas au format 3.00**  
  
     Un curseur ou une icône a été créé dans une version antérieure à la version 3.00.  Vous devez convertir ou recréer le curseur ou l'icône en utilisant le format de la version 3.00 ou ultérieure.  
  
10. **Impossible d'ouvrir le fichier temporaire**  
  
     Le compilateur de ressources\/Visual C\+\+ n'a pas pu ouvrir un fichier temporaire.  Vous n'avez peut\-être pas les droits d'accès en écriture au répertoire ou ce dernier n'existe pas.  Le compilateur de ressources\/Visual C\+\+ tente d'utiliser ces fichiers dans le répertoire spécifié par la variable d'environnement **TMP**, ou dans le répertoire en cours, si aucun autre répertoire n'est spécifié.