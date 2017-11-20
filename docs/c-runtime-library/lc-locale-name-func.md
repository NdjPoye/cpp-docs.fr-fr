---
title: ___lc_locale_name_func | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: ___lc_locale_name_func
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
- msvcr90.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords: ___lc_locale_name_func
dev_langs: C++
helpviewer_keywords: ___lc_locale_name_func
ms.assetid: ef858308-872e-43de-95e0-9b1b4084343e
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a60ca29a61d423186c8b53f23aa9e4d2941f8c57
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="lclocalenamefunc"></a>___lc_locale_name_func
Fonction CRT interne. Récupère le nom de paramètres régionaux actuel du thread.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
wchar_t** ___lc_locale_name_func(void);  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Pointeur vers une chaîne qui contient le nom de paramètres régionaux actuel du thread.  
  
## <a name="remarks"></a>Remarques  
 `___lc_locale_name_func` est une fonction CRT interne qui est utilisée par d'autres fonctions CRT pour obtenir le nom de paramètres régionaux actuel du stockage local des threads pour les données CRT. Ces informations sont également disponibles à l'aide des fonctions [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) ou [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
 Les fonctions CRT internes sont spécifiques à l’implémentation et soumises à modification à chaque nouvelle mise en production. Nous vous déconseillons de les utiliser dans votre code.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`___lc_locale_name_func`|crt\src\setlocal.h|  
  
## <a name="see-also"></a>Voir aussi  
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../c-runtime-library/reference/free-locale.md)