---
title: "Erreur du compilateur C2220 | Microsoft Docs"
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
  - "C2220"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2220"
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2220
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

avertissement considéré comme une erreur \- aucun fichier objet généré  
  
 [\/WX](../../build/reference/compiler-option-warning-level.md) demande au compilateur de considérer tous les avertissements comme des erreurs.  A cause d'une erreur, aucun objet ni fichier exécutable n'a été généré.  
  
 Cette erreur apparaît uniquement lorsque l'indicateur **\/WX** est défini et un avertissement se produit pendant la compilation.  Pour corriger cette erreur, vous devez supprimer chaque avertissement dans votre projet.  
  
### Pour corriger cette erreur, utilisez une des techniques suivantes  
  
-   Résolvez les problèmes qui provoquent des avertissements dans votre projet.  
  
-   Compilez avec un avertissement de inférieur niveau\- par exemple, utilisez **\/W3** au lieu de **\/W4**.  
  
-   Utilisez un pragma [warning](../../preprocessor/warning.md) pour désactiver ou supprimer un avertissement spécifique.  
  
-   N'utilisez pas **\/WX** pour compiler.