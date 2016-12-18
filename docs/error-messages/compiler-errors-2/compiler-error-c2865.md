---
title: "Erreur du compilateur C2865 | Microsoft Docs"
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
  - "C2865"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2865"
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2865
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : comparaison non conforme pour handle\_ou\_pointeur  
  
 Vous ne pouvez effectuer que des comparaisons d'égalité des références aux types [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md) ou [\_\_gc](../../misc/gc.md) pour vérifier s'ils se réfèrent au même objet \(\=\=\) ou à des objets différents \(\!\=\).  
  
 Vous ne pouvez pas les comparer pour les trier car le runtime .NET peut déplacer les objets managés à tout moment, ce qui modifie le résultat du test.