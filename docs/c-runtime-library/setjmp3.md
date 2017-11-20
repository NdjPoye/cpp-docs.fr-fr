---
title: _setjmp3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _setjmp3
apilocation:
- msvcrt.dll
- msvcr90.dll
- msvcr110.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- setjmp3
- _setjmp3
dev_langs: C++
helpviewer_keywords:
- _setjmp3 function
- setjmp3 function
ms.assetid: 6129c2f3-8bac-4fdb-a827-44e1eebba500
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ba68e059224d2d15046730a9ee0058e3114d52ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="setjmp3"></a>_setjmp3
Fonction CRT interne. Nouvelle implémentation de la fonction `setjmp`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _setjmp3(  
   OUT jmp_buf env,  
   int count,  
   (optional parameters)  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `env`  
 Adresse de la mémoire tampon chargée de stocker les informations d'état.  
  
 [in] `count`  
 Nombre de `DWORD` d'informations supplémentaires stockés dans les `optional parameters`.  
  
 [in] `optional parameters`  
 Données supplémentaires transmises par l'intrinsèque `setjmp`. Le premier `DWORD` est un pointeur de fonction utilisé pour dérouler des données supplémentaires et rétablir un état de registre non volatile. Le deuxième `DWORD` est le niveau d'essai à restaurer. Les données supplémentaires éventuelles sont enregistrées dans le tableau de données générique dans `jmp_buf`.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne toujours 0.  
  
## <a name="remarks"></a>Remarques  
 N'utilisez pas cette fonction dans un programme C++. Il s'agit d'une fonction intrinsèque qui ne prend pas en charge C++. Pour plus d'informations sur l'utilisation de `setjmp`, consultez [Utilisation de setjmp/longjmp](../cpp/using-setjmp-longjmp.md).  
  
## <a name="requirements"></a>Spécifications  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [setjmp](../c-runtime-library/reference/setjmp.md)