---
title: "S&#233;curit&#233; dans l&#39;automation &#224; distance | Microsoft Docs"
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
  - "activer des objets"
  - "AllowRemoteActivation"
  - "objets Automation, options de sécurité"
  - "activation d'objet"
  - "Automation à distance, sécurité"
  - "sécurité (MFC)"
  - "sécurité (MFC), Automation à distance"
ms.assetid: 276b300d-c0b5-4bd8-8bf5-0270994b9cfa
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# S&#233;curit&#233; dans l&#39;automation &#224; distance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'automatisation distante prend en charge un niveau de base de sécurité pour permettre à un générateur d'applications de serveur \(ou, au lieu, à son administrateur\) pour spécifier la manière dont un objet spécifique peut être activé à distance.  Tous les objets automatisés sur un système donné peuvent être définis globalement à « rejeter l'activation à distance » ou « autoriser l'activation à distance ».  En outre, et plus souvent, les objets individuels peuvent être affectées de telles fonctionnalités.  L'automatisation distante utilise une clé dans les paramètres du registre pour chaque objet, **AllowRemoteActivation**, pour déterminer si un serveur donné peut être activé à distance.  Si les paramètres de l'ensemble du système utilisent ce mode, chaque objet dans le registre peut se voir affecté cette clé, et l'état individuel de chaque objet peut avoir la valeur « oui » ou « non » comme il convient.  
  
 Si le système hôte exécute Windows NT ou Windows 2000, alors une forme de sécurité alternative est autorisée.  Dans ce cas, l'automatisation à distance utilise la liste de contrôle d'accès \(ACL\) de NT pour spécifier quels utilisateurs ou groupe ou groupes d'utilisateurs peuvent activer un serveur donné à distance.  
  
 Notez que les options de sécurité s'appliquent à l'objet entier; il est impossible de définir les attributs d'une interface spécifique, ou de différentes propriétés ou de méthodes sur cet objet.  
  
 Toutes les options de sécurité peuvent être définies via le gestionnaire de \(RAC\) de connexion d'automatisation à distance.  
  
## Voir aussi  
 [Automation à distance](../mfc/remote-automation.md)