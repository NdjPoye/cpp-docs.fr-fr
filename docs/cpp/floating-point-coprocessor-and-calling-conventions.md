---
title: "Coprocesseur et conventions d&#39;appel &#224; virgule flottante | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "coprocesseur à virgule flottante"
  - "chiffres à virgule flottante"
  - "chiffres à virgule flottante, coprocesseur"
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Coprocesseur et conventions d&#39;appel &#224; virgule flottante
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous écrivez des routines d'assembly pour le coprocesseur à virgule flottante, vous devez conserver le mot de commande à virgule flottante et nettoyer la pile de coprocesseur si vous ne retournez pas de valeur **float** ou **double** \(que votre fonction doit retourner dans ST\(0\)\).  
  
## Voir aussi  
 [Conventions d'appel](../cpp/calling-conventions.md)