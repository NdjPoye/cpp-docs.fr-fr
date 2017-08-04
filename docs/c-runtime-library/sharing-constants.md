---
title: Partage de constantes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SH_DENYNO
- _SH_DENYRD
- _SH_DENYRW
- _SH_DENYWR
- _SH_COMPAT
dev_langs:
- C++
helpviewer_keywords:
- _SH_DENYRW constant
- SH_DENYRD constant
- _SH_COMPAT constant
- _SH_DENYRD constant
- SH_DENYRW constant
- sharing constants
- SH_DENYNO constant
- _SH_DENYWR constant
- SH_DENYWR constant
- _SH_DENYNO constant
- SH_COMPAT constant
ms.assetid: 95fadc3a-55dc-473d-98b5-e8211900465d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: f2cf723738fccb92421f88b6c08405083f08e0fb
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="sharing-constants"></a>Partage de constantes
Constantes pour les modes de partage de fichiers.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
#include <share.h>  
  
```  
  
## <a name="remarks"></a>Remarques  
 L’argument *shflag* détermine le mode de partage, qui se compose d’une ou plusieurs des constantes manifestes. Elles peuvent être combinées avec les arguments *oflag* (voir [Constantes de fichier](../c-runtime-library/file-constants.md)).  
  
 Le tableau suivant répertorie les constantes et leur signification :  
  
|Constante|Signification|  
|--------------|-------------|  
|`_SH_DENYRW`|Refuse l'accès en lecture et en écriture à un fichier|  
|`_SH_DENYWR`|Refuse l'accès en écriture à un fichier|  
|`_SH_DENYRD`|Refuse l'accès en lecture à un fichier|  
|`_SH_DENYNO`|Autorise l'accès en lecture et en écriture|  
|`_SH_SECURE`|Définit le mode sécurisé (lecture partagée, accès en écriture exclusif).|  
  
## <a name="see-also"></a>Voir aussi  
 [_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)
