---
title: __getmainargs, __wgetmainargs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __wgetmainargs
- __getmainargs
apilocation:
- msvcr100.dll
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr110.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- __wgetmainargs
- __getmainargs
dev_langs:
- C++
helpviewer_keywords:
- __wgetmainargs
- __getmainargs
ms.assetid: f72f54eb-9509-4bdf-8752-40fc49055439
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: bd386aba0f5693538d9aae61bcf7c2384b6052bd
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="getmainargs-wgetmainargs"></a>__getmainargs, __wgetmainargs
Appelle l’analyse de ligne de commande et recopie les arguments de `main()` dans les pointeurs transmis.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
int __getmainargs(  
    int * _Argc,   
   char *** _Argv,   
   char *** _Env,   
   int _DoWildCard,  
_startupinfo * _StartInfo);  
  
 int __wgetmainargs (  
   int *_Argc,  
   wchar_t ***_Argv,  
   wchar_t ***_Env,  
   int _DoWildCard,  
   _startupinfo * _StartInfo)  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `_Argc`  
 Entier qui contient le nombre d’arguments qui se suivent dans `argv`. Le paramètre `argc` est toujours supérieur ou égal à 1.  
  
 `_Argv`  
 Tableau de chaînes terminées par le caractère NULL qui représentent les arguments de ligne de commande entrés par l’utilisateur du programme. Par convention, `argv[0]` est la commande avec laquelle le programme est appelé, argv[1] est le premier argument de ligne de commande, et ainsi de suite, jusqu’à argv[argc], qui est toujours NULL. Le premier argument de ligne de commande est toujours `argv[1]` et le dernier `argv[argc - 1]`.  
  
 `_Env`  
 Tableau de chaînes représentant les variables définies dans l’environnement de l’utilisateur. Ce tableau se termine par une entrée NULL.  
  
 `_DoWildCard`  
 Entier qui, avec la valeur 1, développe les caractères génériques dans les arguments de ligne de commande, ou qui, avec la valeur 0, n’a aucun effet.  
  
 `_StartInfo`  
 Autres informations à transmettre à la DLL CRT.  
  
## <a name="return-value"></a>Valeur de retour  
 0 en cas de réussite ; valeur négative en cas d’échec.  
  
## <a name="remarks"></a>Notes  
 Utilisez `__getmainargs` sur les plateformes à caractères non larges et `__wgetmainargs` sur les plateformes à caractères larges (Unicode).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|__getmainargs|internal.h|  
|__wgetmainargs|internal.h|
