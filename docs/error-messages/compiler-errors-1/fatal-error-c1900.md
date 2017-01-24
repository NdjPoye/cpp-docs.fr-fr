---
title: "Erreur irr&#233;cup&#233;rable C1900 | Microsoft Docs"
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
  - "C1900"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1900"
ms.assetid: 3aaa583b-4c1a-45de-aa34-527d806f2cb5
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1900
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Incompatibilité IL de 'outil1' version 'numéro1' et 'outil2' version 'numéro2'  
  
 Les outils exécutés dans différentes passes du compilateur ne correspondent pas.  ***numéro1*** et ***numéro2*** font référence aux dates dans les fichiers.  Par exemple, dans la passe 1, le compilateur frontal s'exécute \(c1.dll\), alors que dans la passe 2, c'est le compilateur principal \(c2.dll\).  Les dates doivent correspondre dans les fichiers.  
  
 Pour résoudre ce problème, assurez\-vous que toutes les mises à jour ont été appliquées à Visual Studio.  Si le problème persiste, utilisez **Programmes et fonctionnalités** dans le panneau de configuration Windows pour réparer ou réinstaller Visual Studio.