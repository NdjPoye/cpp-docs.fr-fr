---
title: "Erreur du compilateur C3309 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3309"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3309"
ms.assetid: 75ee16e3-7d4e-4c41-b3cb-64e9849c3aab
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3309
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'nom\_macro' : le nom du module ne peut pas être une macro ou un mot clé  
  
 La valeur que vous passez à la propriété name de l’attribut de module ne peut pas être un symbole à développer par le préprocesseur. Il doit s’agir d’un littéral de chaîne.  
  
 L’exemple suivant génère l’erreur C3309 :  
  
```  
// C3309.cpp #define NAME MyModule [module(name="NAME")];   // C3309 // Try the following line instead // [module(name="MyModule")]; [coclass] class MyClass { public: void MyFunc(); }; int main() { }  
```