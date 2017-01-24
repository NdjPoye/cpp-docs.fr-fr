---
title: "Overflow. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.VB_E_OVERFLOW"
  - "vs.message.0x800A0097"
ms.assetid: 632387b9-be9c-4744-bcc5-842c45582347
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Overflow.
Une assignation dépasse les limites définies pour la cible de l'affectation.  Cette erreur se produit généralement lorsque l'une des conditions suivantes se vérifie :  
  
-   Le résultat d'une assignation, d'un calcul ou d'une conversion d'un type de données est trop important pour être représenté dans la plage de valeurs autorisées pour ce type de variable.  
  
-   Une assignation à une propriété dépasse la valeur maximale pouvant être acceptée par la propriété.  
  
-   Vous avez essayé d'utiliser un nombre dans un calcul, ce nombre est contraint à un entier, mais le résultat est plus important qu'un entier.  
  
### Pour corriger cette erreur  
  
1.  Assignez la valeur à une variable d'un type pouvant stocker une plage de valeurs plus importante.  
  
     \- ou \-  
  
     Assurez\-vous que votre assignation se situe dans la plage de la propriété pour laquelle elle a été effectuée.