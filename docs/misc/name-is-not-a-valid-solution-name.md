---
title: "&lt;name&gt; is not a valid solution name. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.VS_E_INVALIDSOLUTIONNAME"
  - "vs.message.0x800A00D3"
ms.assetid: 79b7870d-16bd-4527-8ce6-ffb015e7e330
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# &lt;name&gt; is not a valid solution name.
Cette erreur se produit généralement lorsque la commande `File.NewProject` a été entrée dans la fenêtre **Commande** ou dans la zone de texte **Rechercher\/Commande** avec une valeur au format incorrect pour l'argument \/sln:*solutionname*.  
  
### Pour corriger cette erreur  
  
1.  Entrez à nouveau la commande en n'utilisant pas l'argument \/sln:*solutionname*.  Un nom de solution unique sera alors généré.  
  
     \- ou \-  
  
     Vérifiez que le nom de projet ne contient pas d'espaces superflus au début ou à la fin et qu'il ne s'agit pas d'un mot réservé.  Les mots réservés sont entre autres NUL, CON, AUX, COM*x* et LPT*x*, avec *x* compris entre 1 et 9.  
  
## Voir aussi  
 [Commande, fenêtre](../Topic/Command%20Window.md)