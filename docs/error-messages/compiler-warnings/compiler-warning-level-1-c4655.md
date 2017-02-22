---
title: "Avertissement du compilateur (niveau&#160;1) C4655 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4655"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4655"
ms.assetid: 540f2c7a-e4a1-49af-84b4-03eeea1bbf41
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau&#160;1) C4655
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**'**   
 ***symbole* ' : type de variable postérieur à la dernière génération, ou défini différemment à un autre endroit**  
  
 Vous avez modifié ou ajouté un nouveau type de données depuis la dernière génération réussie. Modifier & Continuer ne prend pas en charge les modifications sur les types de données existants.  
  
 Cet avertissement est suivi d’une [erreur irrécupérable C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Pour plus d’informations, consultez [Modifications de code prises en charge](../Topic/Supported%20Code%20Changes%20\(C++\).md).  
  
### Pour supprimer cet avertissement sans mettre fin à la session de débogage en cours  
  
1.  Rétablissez l’état dans lequel se trouvait le type de données avant l’erreur.  
  
2.  Dans le menu **Déboguer**, choisissez **Appliquer les modifications du code**.  
  
### Pour supprimer cette erreur sans modifier votre code source  
  
1.  Dans le menu **Déboguer**, choisissez **Arrêter le débogage**.  
  
2.  Dans le menu **Générer**, choisissez **Générer**.