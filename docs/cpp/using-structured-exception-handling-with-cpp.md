---
title: "Utilisation de la gestion structur&#233;e des exceptions avec C++ | Microsoft Docs"
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
  - "gestion d'exceptions C++, associé à SEH"
  - "gestion structurée des exceptions, avec gestion d'exceptions C++"
ms.assetid: ec34b528-8c26-4429-b24a-6a68553aaa91
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de la gestion structur&#233;e des exceptions avec C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La gestion structurée des exceptions décrite dans ces articles fonctionne avec les fichiers sources C et C\+\+.  Toutefois, elle n'est pas conçue spécifiquement pour C\+\+ et n'est pas recommandée.  Vous pouvez vous assurer que votre code est plus portable en utilisant la gestion des exceptions C\+\+.  En outre, le mécanisme de gestion des exceptions C\+\+ est plus souple, car il peut gérer les exceptions de tout type.  
  
 Microsoft C\+\+ prend désormais en charge le modèle de gestion des exceptions C\+\+, basé sur la norme C\+\+ ANSI.  Ce mécanisme gère automatiquement la destruction des objets locaux pendant le déroulement de la pile.  Si vous écrivez du code C\+\+ à tolérance de panne et que vous souhaitez implémenter la gestion des exceptions, nous vous recommandons vivement d'utiliser la gestion des exceptions C\+\+ plutôt que la gestion structurée des exceptions. \(Notez que bien que le compilateur C\+\+ prenne en charge les constructions de gestion structurée des exceptions comme décrit dans des articles, le compilateur C standard ne prend pas en charge la syntaxe de gestion des exceptions C\+\+.\) Pour plus d'informations sur la gestion des exceptions C\+\+, consultez [Gestion des exceptions C\+\+](../cpp/cpp-exception-handling.md) et le *Manuel de référence C\+\+ annoté* par Margaret Ellis et Bjarne Stroustrup.  
  
## Voir aussi  
 [Gestion structurée des exceptions](../cpp/structured-exception-handling-c-cpp.md)