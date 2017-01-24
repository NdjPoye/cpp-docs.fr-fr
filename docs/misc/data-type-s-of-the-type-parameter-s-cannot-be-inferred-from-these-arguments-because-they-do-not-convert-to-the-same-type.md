---
title: "Impossible de d&#233;duire le ou les types de donn&#233;es du ou des param&#232;tres de type &#224; partir de ces arguments, car ils ne sont pas convertis vers le m&#234;me type | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36659"
  - "bc36659"
  - "vbc36656"
  - "bc36656"
helpviewer_keywords: 
  - "BC36659"
  - "BC36656"
ms.assetid: 0aa809da-3b44-4d78-b3c5-0a148bdf7ce8
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Impossible de d&#233;duire le ou les types de donn&#233;es du ou des param&#232;tres de type &#224; partir de ces arguments, car ils ne sont pas convertis vers le m&#234;me type
Impossible de déduire le ou les types de données du ou des paramètres de type à partir de ces arguments, car ils ne sont pas convertis vers le même type. La spécification explicite du ou des types de données peut permettre de corriger cette erreur.  
  
 Cette erreur se produit quand la résolution de surcharge a échoué. Elle entraîne l’affichage d’un message subordonné qui indique pourquoi un candidat de surcharge particulier a été éliminé. L’erreur explique que le compilateur ne peut pas utiliser l’inférence de type pour rechercher des types de données pour les paramètres de type qui sont compatibles avec les arguments.  
  
> [!NOTE]
>  Quand la spécification des arguments n’est pas une option \(par exemple pour les opérateurs de requête dans les expressions de requête\), le message d’erreur apparaît sans la deuxième phrase.  
  
 Pour plus d’informations et d’exemples, consultez [Impossible de déduire le ou les types de données du ou des paramètres de type dans la méthode '\<nom\_méthode\>' à partir de ces arguments, car ils ne sont pas convertis vers le même type](../misc/data-type-s-of-the-type-parameter-s-in-method-methodname-cannot-be-inferred-from-these-arguments-because-they-do-not-convert-to-the-same-type.md).  
  
 **ID d’erreur :** BC36659 et BC36656  
  
## Voir aussi  
 [Relaxed Delegate Conversion](../Topic/Relaxed%20Delegate%20Conversion%20\(Visual%20Basic\).md)   
 [Generic Procedures in Visual Basic](../Topic/Generic%20Procedures%20in%20Visual%20Basic.md)   
 [Overload Resolution](../Topic/Overload%20Resolution%20\(Visual%20Basic\).md)