---
title: "Optimisation de la persistance et de l&#39;initialisation | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles ActiveX MFC, optimiser"
  - "optimisation, contrôles ActiveX"
  - "optimiser les performances, contrôles ActiveX"
  - "performances, contrôles ActiveX"
ms.assetid: e821e19e-b9eb-49ab-b719-0743420ba80b
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Optimisation de la persistance et de l&#39;initialisation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Par défaut, la persistance et l'initialisation d'un contrôle sont gérés par la fonction membre d'`DoPropExchange`.  Dans un contrôle type, cette fonction contient les appels à plusieurs fonctions de **PX\_** \(`PX_Color`, `PX_Font`, etc.\), un pour chaque propriété.  
  
 Cette solution présente l'avantage qu'une seule implémentation d'`DoPropExchange` peut être utilisée pour l'initialisation, pour la persistance au format binaire, et pour la persistance du soi\-disant format « conteneur des propriétés » utilisé par certains conteneurs.  Cette fonction fournit toutes les informations sur les propriétés et leurs valeurs par défaut dans une fonction pratique.  
  
 Toutefois, cette généralité provient au détriment de l'efficacité.  Les fonctions de **PX\_** reçoivent leur souplesse via des implémentations multicouche en conséquence moins efficaces que plus direct, mais moins souples, les approches.  En outre, si le contrôle est passé comme valeur par défaut une fonction de **PX\_**, cette valeur par défaut doit être fournie chaque fois, même dans les situations où la valeur par défaut ne peut pas nécessairement être utilisée.  Si la valeur par défaut est une tâche triviale \(par exemple, si la valeur est obtenue à partir de propriété ambiante\), les du travail non nécessaire est effectuée dans les cas où la valeur par défaut n'est pas utilisée.  
  
 Vous pouvez améliorer la représentation binaire de la persistance de votre contrôle en entrant la fonction d'`Serialize` de votre contrôle.  L'implémentation par défaut de cette fonction membre passe un appel à la fonction d'`DoPropExchange`.  En la remplaçant, vous pouvez fournir une implémentation plus directe pour la persistance binaire.  Par exemple, observez cette déclaration : `DoPropExchange`  
  
 [!code-cpp[NVC_MFC_AxOpt#1](../mfc/codesnippet/CPP/optimizing-persistence-and-initialization_1.cpp)]  
  
 Pour améliorer les performances de la persistance binaire de ce contrôle, vous pouvez remplacer la fonction d'`Serialize` comme suit :  
  
 [!code-cpp[NVC_MFC_AxOpt#2](../mfc/codesnippet/CPP/optimizing-persistence-and-initialization_2.cpp)]  
  
 La variable locale d'`dwVersion` permet de détecter la version de l'état permanent du contrôle chargé ou enregistré.  Vous pouvez utiliser cette variable au lieu d'appeler [CPropExchange::GetVersion](../Topic/CPropExchange::GetVersion.md).  
  
 Pour enregistrer un petit espace au format permanent pour une propriété de **BOOL** \(et de la gestion compatible avec le format produit par `PX_Bool`\), vous pouvez stocker la propriété définie **BYTE**, comme suit :  
  
 [!code-cpp[NVC_MFC_AxOpt#3](../mfc/codesnippet/CPP/optimizing-persistence-and-initialization_3.cpp)]  
  
 Notez que dans le cas de charge, une variable temporaire est utilisé et que sa valeur est affectée, plutôt qu' `m_boolProp` de conversion vers une référence de **BYTE**.  La technique de conversion provoquerait un seul octet d'`m_boolProp` modifié, laissant les octets restants non initialisés.  
  
 Pour le même contrôle, vous pouvez optimiser l'initialisation du contrôle en remplaçant [COleControl::OnResetState](../Topic/COleControl::OnResetState.md) comme suit :  
  
 [!code-cpp[NVC_MFC_AxOpt#4](../mfc/codesnippet/CPP/optimizing-persistence-and-initialization_4.cpp)]  
  
 Bien qu' `Serialize` et `OnResetState` ont été substitués, la fonction d'`DoPropExchange` doit être conservée intacte parce qu'elle est encore utilisée pour la persistance du format de conteneur des propriétés.  Il est important de conserver les trois de ces fonctions pour vous assurer que le contrôle gère ses propriétés régulièrement, indépendamment de le mécanisme de persistance le conteneur utilise.  
  
## Voir aussi  
 [Contrôles ActiveX MFC : optimisation](../mfc/mfc-activex-controls-optimization.md)