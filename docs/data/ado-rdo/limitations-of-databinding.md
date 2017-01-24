---
title: "Limites de la liaison de donn&#233;es | Microsoft Docs"
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
  - "liaison de données (C++), limitations en Visual C++"
ms.assetid: 376d7738-5252-4caa-adda-a5486ab2a2a2
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Limites de la liaison de donn&#233;es
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La liaison de données est un puissant mécanisme de création rapide d'applications de données.  Cependant, l'architecture actuelle des contrôles de liaison de données est fondamentalement à deux couches.  
  
## Extensibilité  
 Les contrôles liés aux données ADO peuvent accéder aux données uniquement à partir du contrôle de données ADO.  Les contrôles liés aux données RDO peuvent accéder aux données uniquement à partir du contrôle RemoteData RDO.  Pour le contrôle RemoteData RDO, il n'existe aucune autre solution en dehors de l'utilisation de l'architecture à deux niveaux, qui fait que le serveur de base de données reçoit directement toutes les demandes de récupération de données.  Pour éviter la connexion directe au serveur de base de données, écrivez un fournisseur qui autorise l'accès aux objets de données et business de couche intermédiaire.  Le contrôle de données ADO se connecte à ces objets plutôt qu'au serveur de base de données.  Ces objets de couche intermédiaire peuvent être mis en cache et managés dans un serveur de transactions tel que les services COM\+ 1.0.  
  
## Versioning et distribution  
 Quand de nouvelles versions de contrôles sont introduites, l'application doit être testée avec les nouvelles versions.  Si une autre application est installée sur l'ordinateur de l'utilisateur et que celui\-ci contient une version des contrôles différente, l'application doit être vérifiée.  Enfin, quand de nouvelles versions de contrôles sont introduites, les nouveaux contrôles doivent être distribués aux utilisateurs de l'application.  
  
 **Pilotes et fournisseurs**  
  
 La liaison de données ne vaut que ce que vaut le pilote ODBC ou le fournisseur OLE DB que vous utilisez.  Dans la mesure où les pilotes et les fournisseurs sont chargés d'exposer les données aux contrôles de données, il est important de s'assurer que le pilote ou le fournisseur prenne en charge la fonctionnalité dont vous avez besoin.  Une fois que vous avez sélectionné un pilote ou un fournisseur, vous devez vous assurer que les utilisateurs ont le pilote ou le fournisseur installé.  Cela inclut l'installation de tout logiciel intermédiaire \(middleware\) requis par le pilote ou le fournisseur.  Par exemple, pour la connectivité ODBC Oracle, l'utilisateur doit avoir installé non seulement un pilote ODBC Oracle mais également le logiciel intermédiaire Oracle SQL\*Net.  Pour la connectivité aux serveurs Oracle 7.3, le pilote ODBC Microsoft Oracle est recommandé.  
  
 **Facilité de programmation**  
  
 Dans la mesure où les contrôles ActiveX ont été conçus pour servir de composants de boîte noire, la facilité de programmation est limitée à l'accès par le développeur aux interfaces du contrôle.  Dans le modèle de liaison de données de l'Éditeur de ressources, ce comportement est implémenté par l'intermédiaire des [Classes wrapper](../../data/ado-rdo/wrapper-classes.md) générées par l'Assistant Insérer un contrôle ActiveX.  Si l'Assistant ne parvient pas à détecter une coclasse, aucune classe wrapper n'est générée et l'accès par programme n'est pas possible.  
  
 Malgré ces limites, la liaison de données permet la création rapide de prototypes d'applications de données à l'aide de Visual C\+\+.  Si la rapidité est un critère de développement important, vous devez alors prendre en compte la liaison de données lors de la création de votre application.  
  
## Voir aussi  
 [Liaison de données avec des contrôles ActiveX dans Visual C\+\+](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)