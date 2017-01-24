---
title: "Fichiers&#160;.obj en tant qu&#39;entr&#233;e de l&#39;&#201;diteur de liens | Microsoft Docs"
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
  - "fichiers .obj en tant qu'entrée dans l'éditeur de liens"
  - "fichiers COFF"
  - "LINK (outil C++), fichiers .obj"
  - "éditeur de liens (C++), fichiers OBJ en tant qu'entrée dans"
  - "fichiers OBJ en tant qu'entrée dans l'éditeur de liens"
  - "fichiers objets, sortie de l'éditeur de liens"
  - "fichiers objets OMF"
ms.assetid: 3028e423-8b10-4972-8eb4-6e9ae58f0a26
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fichiers&#160;.obj en tant qu&#39;entr&#233;e de l&#39;&#201;diteur de liens
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'outil éditeur de liens \(LINK.EXE\) accepte des fichiers .obj qui sont au format COFF \(Common Object File Format\).  
  
## Notes  
 Microsoft fournit un document téléchargeable qui définit le format COFF.  Pour plus d'informations, téléchargez la révision 8.1 ou une version ultérieure de la [spécification du format de fichier Microsoft PE \(Portable Executable\) et COFF \(Common Object File Format\) \(page éventuellement en anglais\)](http://go.microsoft.com/fwlink/?LinkId=93292).  
  
## Prise en charge Unicode  
 Depuis Visual Studio 2005, le compilateur Microsoft Visual C\+\+ prend en charge des caractères Unicode dans les identificateurs comme définis par les normes C et C\+\+ ISO\/IEC.  Les versions antérieures du compilateur ont pris en charge uniquement des caractères ASCII dans les identificateurs.  Pour prendre en charge Unicode dans les noms de fonctions, de classes et statiques, le compilateur et l'éditeur de liens utilisent l'encodage UTF\-8 Unicode pour les symboles COFF dans les fichiers .obj.  L'encodage UTF\-8 offre une compatibilité ascendante avec l'encodage ASCII utilisé par les versions antérieures de Visual Studio.  
  
 Pour plus d'informations sur le compilateur et l'éditeur de liens, consultez [Prise en charge Unicode dans le compilateur et l'éditeur de liens](../../build/reference/unicode-support-in-the-compiler-and-linker.md).  Pour plus d'informations sur la norme Unicode, consultez l'organisation [Unicode](http://go.microsoft.com/fwlink/?LinkId=37123).  
  
## Voir aussi  
 [Fichiers d'entrée LINK](../../build/reference/link-input-files.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)   
 [Prise en charge pour Unicode](../../text/support-for-unicode.md)   
 [Prise en charge Unicode dans le compilateur et l'éditeur de liens](../../build/reference/unicode-support-in-the-compiler-and-linker.md)   
 [Norme Unicode](http://go.microsoft.com/fwlink/?LinkId=37123)   
 [Spécification de format COFF](http://go.microsoft.com/fwlink/?LinkId=93292)