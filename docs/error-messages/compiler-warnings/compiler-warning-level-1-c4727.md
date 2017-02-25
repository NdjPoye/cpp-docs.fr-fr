---
title: "Avertissement du compilateur (niveau 1) C4727 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4727"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4727"
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Avertissement du compilateur (niveau 1) C4727
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"PCH nommé pch\_file comportant le même horodatage dans fichier\_obj\_1 et fichier\_obj\_2.  Utilisation du premier PCH.  
  
 L'erreur C4727 se produit lors de la compilation de plusieurs modules \(compilands\) avec **\/Yc**, où le compilateur a pu marquer tous les fichiers .obj avec le même horodatage .pch.  
  
 Pour y remédier, compilez un fichier source avec **\/Yc \/c** \(qui crée un fichier .pch\), et compilez les autres séparément avec **\/Yu \/c** \(qui utilise un fichier .pch\), puis liez\-les ensemble.  
  
 Ainsi, si vous avez procédé de la manière décrite ci\-dessous et si l'erreur C4727 s'est produite :  
  
 **cl \/clr \/GL a.cpp b.cpp c.cpp \/Ycstdafx.h**  
  
 Vous devez plutôt effectuer les opérations suivantes :  
  
 **cl \/clr \/GL a.cpp \/Ycstdafx.h \/c**  
  
 **cl \/clr \/GL b.cpp c.cpp \/Yustdafx.h \/link a.obj**  
  
 Pour plus d'informations, consultez  
  
-   [\/Yc \(Créer un fichier d'en\-tête précompilé\)](../../build/reference/yc-create-precompiled-header-file.md)  
  
-   [\/Yu \(Utiliser un fichier d'en\-tête précompilé\)](../../build/reference/yu-use-precompiled-header-file.md)