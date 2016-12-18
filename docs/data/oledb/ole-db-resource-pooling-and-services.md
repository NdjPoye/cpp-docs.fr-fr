---
title: "Services et regroupement des ressources OLE&#160;DB | Microsoft Docs"
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
  - "fournisseurs OLE DB, regroupement des ressources"
  - "services OLE DB"
  - "services OLE DB, configuration de fournisseur requise"
  - "OLE DB, regroupement des ressources"
  - "regroupement de ressources (OLE DB), configuration de fournisseur requise"
  - "fournisseurs de services (OLE DB)"
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Services et regroupement des ressources OLE&#160;DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour fonctionner correctement avec le regroupement OLE DB, ou avec n'importe quel service OLE DB, votre fournisseur doit prendre en charge le regroupement de tous les objets.  Il s'agit d'une obligation pour tout fournisseur OLE DB 1.5 ou version ultérieure.  C'est un point crucial pour les services de mise à niveau.  Les fournisseurs qui ne prennent pas en charge l'agrégation ne peuvent pas être regroupés, et aucun service supplémentaire ne peut être fourni.  
  
 Pour être regroupés, les fournisseurs doivent prendre en charge le modèle « Free thread ».  Le regroupement des ressources détermine le modèle de thread du fournisseur en fonction de la propriété **DBPROP\_THREADMODEL**.  
  
 Si le fournisseur a un état de connexion global qui peut changer pendant que la source de données se trouve dans un état initialisé, il doit prendre en charge la nouvelle propriété **DBPROP\_RESETDATASOURCE**.  Cette propriété est appelée avant la réutilisation d'une connexion et donne au fournisseur la possibilité de nettoyer l'état avant son utilisation suivante.  Si le fournisseur ne peut pas nettoyer un état associé à la connexion, il peut retourner **DBPROPSTATUS\_NOTSETTABLE** pour la propriété, et la connexion ne sera pas réutilisée.  
  
 Les fournisseurs qui se connectent à une base de données distante et sont en mesure de détecter si oui ou non cette connexion peut être perdue doivent prendre en charge la propriété **DBPROP\_CONNECTIONSTATUS**.  Cette propriété donne aux services OLE DB la possibilité de détecter les connexions mortes et de s'assurer qu'elles ne sont pas remises dans le regroupement.  
  
 Enfin, l'inscription automatique des transactions ne fonctionne généralement que si elle est implémentée au même niveau que le regroupement.  Les fournisseurs qui gèrent l'inscription automatique des transactions doivent prendre en charge la désactivation de cette inscription en exposant la propriété **DBPROP\_INIT\_OLEDBSERVICES** et en désactivant l'inscription en cas de désélection de **DBPROPVAL\_OS\_TXNENLISTMENT**.  
  
## Voir aussi  
 [Techniques avancées du fournisseur](../../data/oledb/advanced-provider-techniques.md)