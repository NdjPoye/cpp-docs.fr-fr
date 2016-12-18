---
title: "Erreur du compilateur C3533 | Microsoft Docs"
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
  - "C3533"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3533"
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3533
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : un paramètre ne peut pas avoir un type qui contient « auto »  
  
 Une méthode ou paramètre de modèle ne peut pas être déclaré avec le mot clé `auto` si l'option de compilateur automatique par défaut [\/Zc:auto](../../build/reference/zc-auto-deduce-variable-type.md) est appliquée.  
  
### Pour corriger cette erreur  
  
1.  Supprimez le mot clé `auto` de la déclaration de paramètre.  
  
## Exemple  
 L'exemple suivant donne C3535 parce qu'il déclare un paramètre de fonction avec le mot clé `auto` et il est compilé avec **\/Zc:auto**.  
  
```  
// C3533a.cpp  
// Compile with /Zc:auto  
void f(auto j){} // C3533  
```  
  
## Exemple  
 L'exemple suivant donne C3535 parce qu'il déclare un paramètre de modèle avec le mot clé `auto` et il est compilé avec **\/Zc:auto**.  
  
```  
// C3533b.cpp  
// Compile with /Zc:auto  
template<auto T> class C{}; // C3533  
```  
  
## Voir aussi  
 [auto, mot clé](../../cpp/auto-keyword.md)   
 [\/Zc:auto \(déduire le type de variable\)](../../build/reference/zc-auto-deduce-variable-type.md)