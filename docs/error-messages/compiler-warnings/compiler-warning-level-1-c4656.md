---
title: "Avertissement du compilateur (niveau 1) C4656 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4656"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4656"
ms.assetid: b5aaef74-2320-4345-a6ae-b813881a491c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4656
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbole' : type de données nouveau ou modifié depuis la dernière génération, ou défini différemment à un autre endroit  
  
 Vous avez ajouté ou modifié un type de données, ce que le rend nouveau pour votre code source depuis la dernière génération réussie.  Modifier & Continuer ne prend pas en charge les modifications des types de données existants.  
  
 Cet avertissement sera toujours suivi d'une [Erreur irrécupérable C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md).  Pour plus d'informations, consultez [Modifications de code prises en charge](../Topic/Supported%20Code%20Changes%20\(C++\).md).  
  
### Pour supprimer cet avertissement sans mettre fin à la session de débogage en cours  
  
1.  Replacez le type de données dans l'état où il se trouvait avant l'erreur.  
  
2.  Dans le menu **Déboguer**, choisissez **Appliquer les modifications du code**.  
  
### Pour supprimer cette erreur sans modifier votre code source  
  
1.  Dans le menu **Déboguer**, choisissez **Arrêter le débogage**.  
  
2.  Dans le menu **Générer**, cliquez sur **Générer**.