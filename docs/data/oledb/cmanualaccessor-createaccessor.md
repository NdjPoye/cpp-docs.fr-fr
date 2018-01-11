---
title: CManualAccessor::CreateAccessor | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CManualAccessor::CreateAccessor
- CreateAccessor
- ATL.CManualAccessor.CreateAccessor
- CManualAccessor.CreateAccessor
- CManualAccessor::CreateAccessor
dev_langs: C++
helpviewer_keywords: CreateAccessor method
ms.assetid: 594c8d6d-b49a-4818-a9a5-81c8115d4e42
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f313e6d2b13a03a91295c75d52e4e77d5dfda22b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cmanualaccessorcreateaccessor"></a>CManualAccessor::CreateAccessor
Alloue de la mémoire pour la colonne des structures de liaison et initialise les membres de données de colonne.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT CreateAccessor(   
   int nBindEntries,   
   void* pBuffer,   
   DBLENGTH nBufferSize    
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nBindEntries`  
 [in] Nombre de colonnes. Ce nombre doit correspondre au nombre d’appels à la [CManualAccessor::AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md) (fonction).  
  
 `pBuffer`  
 [in] Pointeur vers la mémoire tampon où sont stockés les colonnes de sortie.  
  
 `nBufferSize`  
 [in] La taille de la mémoire tampon en octets.  
  
## <a name="return-value"></a>Valeur de retour  
 Un de la norme `HRESULT` valeurs.  
  
## <a name="remarks"></a>Notes  
 Appelez cette fonction avant d’appeler le `CManualAccessor::AddBindEntry` (fonction).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CManualAccessor (classe)](../../data/oledb/cmanualaccessor-class.md)   
 [Exemple DBVIEWER](../../visual-cpp-samples.md)