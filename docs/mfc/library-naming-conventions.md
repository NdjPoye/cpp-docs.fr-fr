---
title: "Conventions d&#39;affectation de noms aux biblioth&#232;ques | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conventions de codage, noms de bibliothèques MFC"
  - "applications console, versions de bibliothèque MFC"
  - "conventions (C++), noms de bibliothèques MFC"
  - "bibliothèques (C++), statiques"
  - "bibliothèques MFC, conventions d'affectation de noms"
  - "NAFXCW.LIB"
  - "NAFXCWD.LIB"
  - "conventions d'affectation de noms (C++), MFC (bibliothèques de code d'objets)"
  - "bibliothèques de code d'objets"
  - "bibliothèques de code d'objets, MFC (conventions d'affectation de noms)"
ms.assetid: 39fe7d93-5a14-4c6a-b16c-bf318fa01278
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Conventions d&#39;affectation de noms aux biblioth&#232;ques
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les bibliothèques de code objet pour MFC utilisent les conventions suivantes.  Les noms de la bibliothèque ont la forme  
  
 *u*AFX`c`W`d`.LIB  
  
 où les lettres minuscules affichées en italique représentent des espaces réservés pour les spécificateurs dont les significations sont répertoriées dans le tableau suivant :  
  
### Conventions d'affectation de noms aux bibliothèques  
  
|Spécificateur|Valeurs et significations|  
|-------------------|-------------------------------|  
|*u*|ANSI \(N\) ou Unicode \(U\)|  
|`c`|Type de programme à créer : C\=all|  
|`d`|Débogage ou version de sortie : D\=Debug ; omettez le spécificateur pour la version de sortie|  
  
 Le comportement par défaut est de créer une requête Windows ANSI de débogage de plateforme Intel : NAFXCWD.Lib.  Toutes les bibliothèques répertoriées dans le tableau suivant sont prégénérées inclus dans le répertoire \\atlmfc\\lib sur le CD\-ROM Visual C\+\+.  
  
### Conventions d'affectation de noms de la bibliothèque Static\-Link  
  
|Bibliothèque|Description|  
|------------------|-----------------|  
|NAFXCW.LIB|Bibliothèque de Static\-Link de MFC, version préliminaire|  
|NAFXCWD.LIB|Bibliothèque de Static\-Link de MFC, version de débogage|  
|UAFXCW.LIB|Bibliothèque de Static\-Link de MFC avec la prise en charge d'Unicode, version préliminaire|  
|UAFXCWD.LIB|Bibliothèque de Static\-Link de MFC avec la prise en charge d'Unicode, version de débogage|  
  
> [!NOTE]
>  Si vous devez créer une version de bibliothèque, consultez le fichier Readme.txt dans le répertoire atlmfc\\src\\cpc.  Ce fichier décrit à l'aide du makefile fourni avec NMAKE.  
  
 Pour plus d'informations, consultez [Conventions d'affectation des noms pour les DLL MFC](../build/naming-conventions-for-mfc-dlls.md) et [Versions Unicode des bibliothèques MFC](../mfc/unicode-in-mfc.md).  
  
## Voir aussi  
 [Versions de bibliothèque MFC](../mfc/mfc-library-versions.md)