---
title: "Activation et désactivation des Services pour un fournisseur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 60e54d9d02cc819c9eaf7674257d846c537da615
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>Activation et désactivation de services pour un fournisseur
Services OLE DB individuels peuvent être activés ou désactivés par défaut pour toutes les applications qui accèdent à un seul fournisseur. Cela est fait en ajoutant un **OLEDB_SERVICES** CLSID, de l’entrée de Registre sous le fournisseur avec un `DWORD` valeur spécifiant les services pour activer ou désactiver, comme illustré dans le tableau suivant.  
  
|Services activés par défaut|Valeur du mot clé|  
|------------------------------|-------------------|  
|Tous les services (par défaut)|0xffffffff|  
|Tous sauf le regroupement et l’inscription automatique|0xFFFFFFFE|  
|Tous sauf le curseur Client|0xfffffffb|  
|Tous sauf le regroupement, l’inscription automatique et le curseur Client|0xfffffff0|  
|Aucun service|0x00000000|  
|Aucune agrégation, tous les services désactivés|\<clé manquante >|  
  
## <a name="see-also"></a>Voir aussi  
 [Activation et désactivation des services OLE DB](../../data/oledb/enabling-and-disabling-ole-db-services.md)