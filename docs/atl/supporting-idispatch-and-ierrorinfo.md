---
title: "Prise en charge de IDispatch et IErrorInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IErrorInfo"
  - "IDispatch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "prise en charge de la classe IDispatch dans ATL"
  - "classe IDispatchImpl"
  - "prise en charge de la classe IErrorInfo dans ATL"
  - "ISupportErrorInfoImpl (méthode)"
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Prise en charge de IDispatch et IErrorInfo
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser la classe de modèle [IDispatchImpl](../atl/reference/idispatchimpl-class.md) pour fournir une implémentation par défaut de la partie d' `IDispatch Interface` de toutes les interfaces doubles sur votre objet.  
  
 Si votre objet utilise l'interface d' `IErrorInfo` pour stocker des erreurs au client, votre objet doit prendre en charge l'interface d' `ISupportErrorInfo Interface` .  La classe de modèle [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) offre un moyen simple d'implémenter ce scénario si vous avez une interface unique qui génère des erreurs sur votre objet.  
  
## Voir aussi  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)