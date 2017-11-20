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
ms.openlocfilehash: 24da0ab4b3ab27cdb9a70c0f9cc05e3ca86e117d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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