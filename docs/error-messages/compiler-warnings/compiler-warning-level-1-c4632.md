---
title: "Avertissement du compilateur (niveau 1) C4632 | Microsoft Docs"
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
  - "C4632"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4632"
ms.assetid: 9e35d205-cf21-4e34-8bd5-e1e7b0e2cdd3
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4632
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

commentaire de document XML : fichier \- accès refusé : raison  
  
 Le chemin d'accès au fichier .xdc \(`file`\) n'était pas valide, et aucun fichier .xdc n'a été créé.  
  
 L'exemple suivant génère l'erreur C4632 :  
  
```  
// C4632.cpp  
// compile with: /clr /docv:\\falsedir /LD /W1  
// C4632 expected  
  
/// Text for class MyClass.  
public ref class MyClass {};  
```