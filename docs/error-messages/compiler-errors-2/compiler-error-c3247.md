---
title: "Erreur du compilateur C3247 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3247"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3247"
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3247
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe1' : une coclasse ne peut pas hériter d’une autre coclasse 'classe2'  
  
 Une classe marquée avec l’attribut [coclass](../../windows/coclass.md) ne peut pas hériter d’une classe marquée avec l’attribut `coclass`.  
  
 L’exemple suivant génère l’erreur C3247 :  
  
```  
// C3247.cpp [module(name="MyLib")]; [coclass] class a { }; [coclass] class b : public a {   // C3247 }; int main() { }  
```