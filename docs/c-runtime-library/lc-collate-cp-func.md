---
title: ___lc_collate_cp_func | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: ___lc_collate_cp_func
apilocation:
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords: ___lc_collate_cp_func
dev_langs: C++
helpviewer_keywords: ___lc_collate_cp_func
ms.assetid: 46ccc084-7ac9-4e5d-9138-e12cb5845615
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 36eed0a5592b41dd4f9f57c1f2f6c395d0bb784a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="lccollatecpfunc"></a>___lc_collate_cp_func
Fonction CRT interne. Récupère la page de code de classement active du thread.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
UINT ___lc_codepage_func(void);  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Page de code de classement active du thread.  
  
## <a name="remarks"></a>Remarques  
 `___lc_collate_cp_func` est une fonction CRT interne utilisée par d'autres fonctions CRT pour obtenir la page de code de classement active à partir du stockage local des threads pour les données CRT. Ces informations sont également disponibles à l'aide de la fonction [_get_current_locale](../c-runtime-library/reference/get-current-locale.md).  
  
 Les fonctions CRT internes sont spécifiques à l’implémentation et soumises à modification à chaque nouvelle mise en production. Nous vous déconseillons de les utiliser dans votre code.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`___lc_collate_cp_func`|crt\src\setlocal.h|  
  
## <a name="see-also"></a>Voir aussi  
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../c-runtime-library/reference/free-locale.md)