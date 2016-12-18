---
title: "Activation et d&#233;sactivation de services pour un fournisseur | Microsoft Docs"
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
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Activation et d&#233;sactivation de services pour un fournisseur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les différents services OLE DB peuvent être activés ou désactivés par défaut pour toutes les applications ayant accès à un seul fournisseur.  Pour cela, il faut ajouter une entrée du Registre **OLEDB\_SERVICES** sous le CLSID du fournisseur, avec une valeur `DWORD` spécifiant les services à activer ou à désactiver, comme illustré dans le tableau suivant :  
  
|Services activés par défaut|Valeur mot clé|  
|---------------------------------|--------------------|  
|Tous les services \(par défaut\)|0xffffffff|  
|Tous sauf le regroupement et l'inscription automatique|0xfffffffe|  
|Tous sauf le curseur client|0xfffffffb|  
|Tous sauf le regroupement, l'inscription automatique et le curseur client|0xfffffff0|  
|Pas de services|0x00000000|  
|Pas de regroupement, tous les services désactivés|\<clé manquante\>|  
  
## Voir aussi  
 [Activation et désactivation des services OLE DB](../../data/oledb/enabling-and-disabling-ole-db-services.md)