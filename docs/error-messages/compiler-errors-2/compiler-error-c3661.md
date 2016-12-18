---
title: "Erreur du compilateur C3661 | Microsoft Docs"
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
  - "C3661"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3661"
ms.assetid: 50793fd1-1829-4b29-ad0d-094ef2068b43
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3661
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

méthodes à substituer introuvables dans la liste des substitutions explicites  
  
 Une substitution explicite a spécifié un ou plusieurs noms de types.  Toutefois, aucune fonction ne possédait la signature nécessaire dans le ou les types qui correspondaient à la signature de la fonction de substitution.  Si vous essayez de substituer en vous basant sur le nom de type, il doit exister une ou plusieurs fonctions virtuelles du ou des types spécifié\(s\) qui correspondent à la signature de la fonction de substitution.  
  
 Pour plus d'informations, consultez [Substitutions explicites](../../windows/explicit-overrides-cpp-component-extensions.md).