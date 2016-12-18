---
title: "Erreur du compilateur C2011 | Microsoft Docs"
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
  - "C2011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2011"
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : redéfinition du type 'type'  
  
 L'identificateur était déjà défini comme `type`.  Recherchez les redéfinitions de l'identificateur.  
  
 L'erreur C2011 peut aussi apparaître si vous importez un fichier d'en\-tête ou une bibliothèque de types plusieurs fois dans le même fichier.  Pour empêcher plusieurs inclusions des types définis dans un fichier d'en\-tête, utilisez des protections de type include ou une directive `#pragma` [once](../../preprocessor/once.md) dans le fichier d'en\-tête.  
  
 Si vous devez rechercher la déclaration initiale du type redéfini, vous pouvez utiliser l'indicateur [\/P](../../build/reference/p-preprocess-to-a-file.md) du compilateur pour générer la sortie prétraitée passée au compilateur.  Vous pouvez utiliser les outils de recherche de texte pour rechercher des instances de l'identificateur redéfini dans le fichier de sortie.  
  
 L'exemple suivant génère l'erreur C2011 et montre une manière de la corriger :  
  
```  
// C2011.cpp  
// compile with: /c  
struct S;  
union S;   // C2011  
union S2;   // OK  
```