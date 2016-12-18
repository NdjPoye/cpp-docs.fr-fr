---
title: "Avertissement du compilateur (niveau 3) C4192 | Microsoft Docs"
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
  - "C4192"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4192"
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4192
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

exclusion automatique de 'nom' lors de l'importation de la bibliothèque de types 'bibliothèque'  
  
 Une bibliothèque `#import` contient un élément, *nom*, aussi défini dans les en\-têtes systèmes Win32.  En raison des restrictions liées aux bibliothèques de types, les noms comme **IUnknown** ou GUID sont souvent définis dans une bibliothèque de types en dupliquant la définition provenant des en\-têtes système.  `#import` détectera ces éléments et refusera de les incorporer dans les fichiers d'en\-tête .tlh et .tli.  
  
 Pour substituer ce comportement, utilisez `#import` attributs [no\_auto\_exclude](../../preprocessor/no-auto-exclude.md) et [include\(\)](../../preprocessor/include-parens.md).