---
title: CBookmark::CBookmark | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CBookmark<0>.CBookmark<0>
- CBookmark::CBookmark
- ATL.CBookmark.CBookmark
- CBookmark.CBookmark
- CBookmark
- ATL::CBookmark<0>::CBookmark<0>
- ATL.CBookmark<0>.CBookmark<0>
- CBookmark<0>::CBookmark<0>
- ATL::CBookmark::CBookmark
dev_langs: C++
helpviewer_keywords: CBookmark class, constructor
ms.assetid: 84f4ad2b-67d4-4ba3-8b2b-656a66fb6298
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d0b38e91830157621835ad12edaeb37c24b8e11d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="cbookmarkcbookmark"></a>CBookmark::CBookmark
Constructeur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      CBookmark( );   
CBookmark(  
   DBLENGTH nSize   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nSize`  
 [in] Taille de la mémoire tampon du signet en octets.  
  
## <a name="remarks"></a>Remarques  
 La première fonction définit la mémoire tampon **NULL** et la taille de mémoire tampon à 0. La deuxième fonction définit la taille de mémoire tampon sur `nSize`et la mémoire tampon vers un tableau d’octets de `nSize` octets.  
  
> [!NOTE]
>  Cette fonction est disponible uniquement dans **CBookmark\<0 >**.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CBookmark, classe](../../data/oledb/cbookmark-class.md)