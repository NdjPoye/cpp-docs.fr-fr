---
title: fwide | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fwide
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- fwide
dev_langs:
- C++
helpviewer_keywords:
- fwide function
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e38bce95a26bd8b128a048768870c63f7de9da9f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="fwide"></a>fwide
Non implémenté.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int fwide(  
   FILE *stream,  
   int mode;  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `stream`  
 Pointeur désignant la structure `FILE` (ignoré).  
  
 `mode`  
 La nouvelle largeur du flux : positive pour un caractère large, négative pour un octet, zéro pour laisser inchangé. (Cette valeur est ignorée.)  
  
## <a name="return-value"></a>Valeur de retour  
 Cette fonction retourne simplement `mode`.  
  
## <a name="remarks"></a>Notes  
 La version actuelle de cette fonction n’est pas conforme à la norme.  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`fwide`|\<wchar.h>|  
  
 Pour plus d'informations, voir [Compatibilité](../../c-runtime-library/compatibility.md).