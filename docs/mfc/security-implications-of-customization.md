---
title: "Implications en mati&#232;re de s&#233;curit&#233; de la personnalisation | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC Feature Pack, sécurité"
  - "sécurité, MFC Feature Pack"
ms.assetid: 9be96b12-be38-43bd-a133-5d671265f7a1
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Implications en mati&#232;re de s&#233;curit&#233; de la personnalisation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit la faiblesse potentielle de sécurité dans MFC.  
  
## Faiblesse de sécurité potentielle  
 MFC autorise l'utilisateur à personnaliser l'allure d'une interface utilisateur de l'application, par exemple, l'apparence des boutons et des icônes.  MFC gère également des outils définis par l'utilisateur, qui permettent à l'utilisateur d'exécuter des commandes d'environnement.  Une faille de sécurité surgit parce que les paramètres personnalisés de l'application sont stockés dans le profil utilisateur dans le Registre.  Quiconque a accès au Registre peut modifier ces paramètres ainsi que l'apparence ou le comportement de l'application.  Par exemple, un administrateur sur l'ordinateur peut emprunter l'identité d'un utilisateur à l'origine de l'application de l'utilisateur pour exécuter des applications arbitraires \(même à partir d'un partage réseau\).  
  
## Solutions  
 Nous recommandons l'un de ces trois méthodes pour fermer les vulnérabilités dans le Registre :  
  
-   Chiffrer les données stockées à  
  
-   Stockez les données dans un fichier sécurisé et non dans le Registre.  
  
     Pour obtenir l'une ou l'autre de ces deux premières méthodes, dérivez une classe de [CSettingsStore Class](../mfc/reference/csettingsstore-class.md) et substituez les méthodes pour implémenter le chiffrement ou le stockage hors du Registre.  
  
-   Désactivez également les personnalisations dans votre application.  
  
## Voir aussi  
 [Personnalisation pour MFC](../mfc/customization-for-mfc.md)