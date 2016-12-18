---
title: "Building an Attributed Program | Microsoft Docs"
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
  - "tlb files"
  - "MIDL"
  - "MIDL, linker output"
  - "IDL files"
  - "tlb files, building attributed programs"
  - ".tlb files, building attributed programs"
  - "IDL files, building"
  - "attributes [C++], building type libraries and .idl files"
  - ".tlb files"
  - ".idl files, building"
  - "type libraries, linker options for building"
ms.assetid: 04997b5f-bf2c-46ec-b868-c4adebbef5f4
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Building an Attributed Program
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Après avoir mis des attributs Visual C\+\+ dans votre code source, vous pouvez souhaiter que le compilateur Visual C\+\+ pour générer une bibliothèque de types et le fichier .idl pour vous.  Les options de l'éditeur de liens suivantes décrivent la génération .tlb et les fichiers .idl :  
  
-   [\/IDLOUT](../build/reference/idlout-name-midl-output-files.md)  
  
-   [\/IGNOREIDL](../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)  
  
-   [\/MIDL](../build/reference/midl-specify-midl-command-line-options.md)  
  
-   [\/TLBOUT](../build/reference/tlbout-name-dot-tlb-file.md)  
  
 Certains projets contiennent les fichiers indépendants d'IU .idl.  Celles\-ci sont utilisées pour produire deux ou plusieurs fichiers .tlb et les lier éventuellement dans le bloc de ressource.  ce scénario n'est pas actuellement pris en charge dans Visual C\+\+.  
  
 De plus, l'éditeur de liens Visual C\+\+ obtiendrez toutes les informations d'attribut IDL\-mises en relation avec un seul fichier MIDL.  Il n'y a aucun moyen de générer deux bibliothèques de types d'un projet unique.  
  
## Voir aussi  
 [Concepts](../windows/attributed-programming-concepts.md)