---
title: "Avertissement du compilateur (niveau&#160;4) C4634 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4634"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4634"
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Avertissement du compilateur (niveau&#160;4) C4634
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Commentaire de document XML : application impossible : raison  
  
 Les balises de documentation XML ne peuvent pas être appliquées à toutes les constructions C\+\+.  Par exemple, vous ne pouvez pas ajouter un commentaire de documentation à un espace de noms ou à un modèle.  
  
 Pour plus d’informations, consultez [Documentation XML](../../ide/xml-documentation-visual-cpp.md).  
  
## Exemple  
 L’exemple suivant génère l’avertissement C4634.  
  
```  
// C4634.cpp // compile with: /W4 /doc /c /// This is a namespace.   // C4634 namespace hello { class MyClass  {}; };  
```  
  
## Exemple  
 L’exemple suivant génère l’avertissement C4634.  
  
```  
// C4634_b.cpp // compile with: /W4 /doc /c /// This is a template.   // C4634 template <class T> class MyClass  {};  
```