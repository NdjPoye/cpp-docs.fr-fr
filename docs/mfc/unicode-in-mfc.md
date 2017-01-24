---
title: "Unicode dans MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "chaînes (C++), Unicode"
  - "Unicode (C++), activer"
  - "Unicode (C++), MFC"
  - "caractères larges, encoder"
  - "caractères larges, Unicode"
ms.assetid: 1002004b-4113-4380-bf63-e1570934b793
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Unicode dans MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC prend en charge la norme Unicode standard pour l'encodage des caractères sur les plateformes Windows NT, Windows 2000 et Windows XP.  Les applications Unicode ne peuvent pas s'exécuter sur les plateformes Windows 98.  
  
 Les versions Unicode des bibliothèques MFC sont décrites ci\-dessous :  
  
### Bibliothèques de liens statiques.  
  
|Release|Débogage|Description|  
|-------------|--------------|-----------------|  
|UAFXCW.lib, .pdb|UAFXCWD.lib, .pdb|Bibliothèque de liens statiques Unicode MFC|  
  
### Bibliothèques de liens dynamiques  
  
|Release|Débogage|Description|  
|-------------|--------------|-----------------|  
|MFC100U.lib, .dbg, def, .dll, .map, .pdb, .prf|MFC100UD.lib, .def, .dll, .map, .pdb|Bibliothèque d'importation Unicode MFC \(consultez les notes ci\-dessous pour le compte d'extensions de fichier\)|  
|MFCS100U.lib, .pdb|MFCS100UD.lib, .pdb|Bibliothèque d'importation Unicode MFC contenant le code qui doit être statiquement lié dans une application ou un fichier .dll|  
  
 **Type de fichiers**  
  
-   Les fichiers de bibliothèque d'importation ont l'extension \(.lib\).  
  
-   Les fichiers bibliothèque de liens dynamiques ont l'extension \(.dll\).  
  
-   Les fichiers de définition de module \(.def\) sont des fichiers texte contenant des instructions pour définir un fichier .exe ou un fichier .dll.  
  
-   Les fichiers de la carte \(.map\) sont des fichiers texte contenant des informations que l'éditeur de liens utilise pour lier un programme.  
  
-   Les fichiers de bibliothèque \(.lib\) sont utilisés conjointement avec les versions de la DLL de MFC.  Ces fichiers contiennent du code qui doit être lié statiquement de l'application ou la DLL.  
  
-   Les fichiers de la base de données du programme \(.pdb\) contiennent le débogage et les informations d'état de projet.  
  
-   Les fichiers de débogage \(.dbg\) contiennent des informations \(COFF FPO, et CodeView\) que le débogueur Visual C\+\+ utilise.  
  
 Pour plus d'informations sur les conventions d'affectation de noms, consultez les [Conventions d'affectation de noms de la bibliothèque](../mfc/library-naming-conventions.md).  
  
 Pour plus d'informations sur l'utilisation d'Unicode avec MFC, consultez [Chaînes : Unicode et prise en charge du jeu de caractères multioctets \(MBCS\)](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
## Voir aussi  
 [Concepts](../mfc/mfc-concepts.md)   
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)