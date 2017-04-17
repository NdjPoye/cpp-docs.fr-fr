---
title: "Erreur du compilateur C2978 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2978"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2978"
ms.assetid: 5e7bee82-e266-4ccd-ad2e-ee89606ec5bf
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C2978
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur de syntaxe : 'mot\_clé1' ou 'mot\_clé2' attendu ; type 'mot\_clé3' trouvé ; les paramètres sans type ne sont pas pris en charge dans les génériques  
  
 Une classe générique a été déclarée incorrectement. Pour plus d’informations, consultez [Generics](../../windows/generics-cpp-component-extensions.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C2978.  
  
```  
// C2978.cpp // compile with: /clr /c generic <ref class T>   // C2978 // try the following line instead // generic <typename T>   // OK ref class Utils { static void sort(T elems, size_t size); }; generic <int> // try the following line instead // generic <class T> ref class Utils2 { static void sort(T elems, size_t size); };  
```