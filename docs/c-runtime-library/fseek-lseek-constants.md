---
title: Constantes fseek, _lseek | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SEEK_END
- SEEK_SET
- SEEK_CUR
dev_langs:
- C++
helpviewer_keywords:
- SEEK_SET constant
- SEEK_END constant
- SEEK_CUR constant
ms.assetid: 9deeb13e-5aa3-4c33-80d8-721c80a4de9d
caps.latest.revision: 6
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
ms.openlocfilehash: 7e0ee54703220eee179f186a6bdb1189f596c2c3
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="fseek-lseek-constants"></a>fseek, _lseek, constantes
## <a name="syntax"></a>Syntaxe  
  
```  
  
#include <stdio.h>  
  
```  
  
## <a name="remarks"></a>Remarques  
 L’argument *origin* spécifie la position initiale et peut prendre l’une des constantes manifestes suivantes :  
  
|Constante|Signification|  
|--------------|-------------|  
|`SEEK_END`|Fin du fichier|  
|`SEEK_CUR`|Position actuelle du pointeur de fichier|  
|`SEEK_SET`|Début du fichier|  
  
## <a name="see-also"></a>Voir aussi  
 [fseek, _fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)   
 [_lseek, _lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)
