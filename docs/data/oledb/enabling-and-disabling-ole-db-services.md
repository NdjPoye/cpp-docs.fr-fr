---
title: "Activation et d&#233;sactivation des services OLE&#160;DB | Microsoft Docs"
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
  - "services OLE DB, activer et désactiver"
  - "fournisseurs de services (OLE DB)"
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Activation et d&#233;sactivation des services OLE&#160;DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB Service Component Manager compare les propriétés spécifiées par le consommateur à celles prises en charge par le fournisseur afin de déterminer si des composants de services individuels peuvent être appelés pour répondre à la demande de fonctionnalités étendues formulée par le consommateur.  Par exemple, si une application demande un curseur à défilement alors que le fournisseur prend en charge uniquement un curseur à défilement vers l'avant, le Service Component Manager appelle le composant de service du moteur du curseur client pour fournir une fonctionnalité de défilement.  Si l'application compte sur une fonctionnalité étendue prise en charge par défaut sur le jeu de lignes du fournisseur, et si l'application ne définit pas de manière explicite les propriétés de manière à demander cette fonctionnalité, la fonctionnalité peut ne pas apparaître sur le rowset retourné par le moteur du curseur client.  Pour être interopérable, les applications doivent toujours définir les propriétés de façon à demander explicitement une fonctionnalité étendue quand c'est nécessaire.  
  
 Dans certains cas, il peut être nécessaire de désactiver des services OLE DB particuliers afin d'obtenir un fonctionnement correct des applications existantes qui font des hypothèses sur les caractéristiques d'un fournisseur.  Les services OLE DB permettent de désactiver des services particuliers, ou tous les services, selon une base connexion par connexion ou pour toutes les applications au moyen d'un fournisseur unique.  
  
## Voir aussi  
 [Services et regroupement des ressources OLE DB](../../data/oledb/ole-db-resource-pooling-and-services.md)