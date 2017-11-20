---
title: __p__commode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __p__commode
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords: __p__commode
dev_langs: C++
helpviewer_keywords: __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
caps.latest.revision: "2"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ef1a4830a994a5832b94f794e63046a0c081d55a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="pcommode"></a>__p__commode
Pointe vers la variable globale `_commode`, qui spécifie le *mode de validation de fichiers* par défaut pour les opérations d’E/S de fichier.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
int * __p__commode(  
   );  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Pointeur vers la variable globale `_commode`.  
  
## <a name="remarks"></a>Notes  
 La fonction `__p__commode` est exclusivement réservée à un usage interne et ne doit pas être appelée à partir du code utilisateur.  
  
 Le mode de validation de fichiers spécifie quand les données critiques sont écrites sur le disque. Pour plus d’informations, consultez [fflush](../c-runtime-library/reference/fflush.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|__p\__commode|internal.h|