---
title: "Fichiers générés par l’Assistant fournisseur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 27fb95e5dc1c417d3dfb03217463a8ef683f3710
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="provider-wizard-generated-files"></a>Fichiers générés par l'Assistant Fournisseur
L’Assistant fournisseur OLE DB ATL génère les fichiers suivants. Les rubriques suivantes utilisent le nom court « MyProvider », mais les noms de fichiers exacts varient selon le choix effectué lors de la création du fournisseur.  
  
|Nom de fichier|Description|  
|---------------|-----------------|  
|MyProviderRS.cpp|Contient l’application d’assistance de la commande `Execute` (méthode) et le mappage de colonnes du fournisseur.|  
|MyProviderDS.h|Implémente l’objet de source de données. Ce fichier d’en-tête contient le mappage de propriété pour les propriétés de source de données.|  
|MyProviderRS.h|Implémente les objets command et rowset. Ce fichier d’en-tête contient le mappage de propriété pour les propriétés d’ensemble de lignes et commande.|  
|MyProviderSess.h|Implémente l’objet de session. Ce fichier d’en-tête contient le mappage de propriété pour les propriétés de la session.|  
|MyProvider.rgs|Contient les objets inscrits générés par l’Assistant fournisseur OLE DB.|  
  
## <a name="see-also"></a>Voir aussi  
 [Création d’un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)