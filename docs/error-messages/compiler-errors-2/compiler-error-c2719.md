---
title: "Erreur du compilateur C2719 | Microsoft Docs"
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
  - "C2719"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2719"
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2719
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'paramètre' : le paramètre formel avec \_\_declspec\(align\('\#'\)\) ne sera pas aligné  
  
 Le modificateur [align](../../cpp/align-cpp.md) `__declspec` n'est pas autorisé sur les paramètres de fonction.  L'alignement des paramètres de fonction est contrôlé par la convention d'appel utilisée.  Pour plus d'informations, voir [Conventions d'appel](../../cpp/calling-conventions.md).  
  
 L'exemple suivant génère l'erreur C2719 et montre comment la corriger :  
  
```  
// C2719.cpp  
void func(int __declspec(align(32)) i);   // C2719  
// try the following line instead  
// void func(int i);  
```