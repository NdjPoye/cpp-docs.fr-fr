---
title: "Connexions Oracle | Microsoft Docs"
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
  - "connexions (C++), bases de données"
  - "connexions de base de données (C++), Oracle"
  - "bases de données (C++), connecter à"
  - "Oracle (C++), créer des connexions"
  - "Oracle (bases de données) (C++)"
  - "Oracle (bases de données) (C++), connexions"
ms.assetid: d317e763-44aa-47c9-abe8-261d513d894f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Connexions Oracle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lors de la configuration d'un DSN ODBC Oracle ou d'une connexion OLE DB, les composants côté client SQL\*Net Oracle doivent être installés.  SQL\*Net est la couche de transport réseau d'Oracle.  La plupart des pilotes ODBC Oracle, y compris le pilote Microsoft et la table des fournisseurs Microsoft OLE DB Oracle, appellent directement cette couche SQL\*Net.  
  
 Après la configuration de SQL\*Net, notez la chaîne de connexion SQL\*Net.  En général, elle est composée d'un spécificateur pour le nom de serveur de base de données Oracle et du type de protocole réseau \(comme TCP\/IP et canaux nommés\).  Souvent, la chaîne de connexion SQL\*Net est mappée à un alias.  En ce cas, il suffit de noter l'alias.  Pour plus d'informations sur la manière de configurer SQL\*Net, contactez votre administrateur de bases de données Oracle, consultez la documentation SQL\*Net ou le fichier d'aide du pilote ODBC Oracle pour obtenir un exemple de chaîne de connexion.  
  
## Voir aussi  
 [Création de connexions de base de données](../../data/ado-rdo/creating-database-connections.md)