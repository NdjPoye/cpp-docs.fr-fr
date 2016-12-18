---
title: "Erreur du compilateur C3537 | Microsoft Docs"
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
  - "C3537"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3537"
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3537
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : impossible d'effectuer un cast dans un type qui contient « auto ».  
  
 Vous ne pouvez pas effectuer un cast d'une variable dans le type indiqué parce que le type contient le mot clé `auto` et l'option de compilateur automatique par défaut [\/Zc:auto](../../build/reference/zc-auto-deduce-variable-type.md) est appliquée.  
  
## Exemple  
 Le code suivant donne C3537 parce que les variables sont castées dans un type qui contient le mot clé `auto`.  
  
```  
// C3537.cpp  
// Compile with /Zc:auto  
int main()  
{  
   int value = 123;  
   auto(value);                        // C3537  
   (auto)value;                        // C3537  
   auto x1 = auto(value);              // C3537  
   auto x2 = (auto)value;              // C3537  
   auto x3 = static_cast<auto>(value); // C3537  
   return 0;  
}  
```  
  
## Voir aussi  
 [auto, mot clé](../../cpp/auto-keyword.md)