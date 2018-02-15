---
title: setjmp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- setjmp
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
- setjmp
dev_langs:
- C++
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ef5c4b0e026090718fc02dd109a1fccb91152010
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="setjmp"></a>setjmp
Enregistre l’état actuel du programme.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int setjmp(  
   jmp_buf env   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `env`  
 Variable dans laquelle l’environnement est stocké.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne la valeur 0 après l’enregistrement de l’environnement de pile. Si `setjmp` est retourné à la suite d’un appel `longjmp`, elle retourne l’argument `value` de `longjmp` ou, si l’argument `value` de `longjmp` est égal à 0, `setjmp` retourne 1. Aucun retour d'erreur.  
  
## <a name="remarks"></a>Notes  
 La fonction `setjmp` enregistre un environnement de pile, que vous pouvez restaurer par la suite à l’aide de `longjmp`. Quand elles sont utilisées ensemble, les fonctions `setjmp` et `longjmp` offrent un moyen d’exécuter un `goto` non local. Elles sont généralement utilisées pour passer le contrôle d’exécution au code de gestion des erreurs ou au code de récupération dans une routine appelée précédemment sans utiliser les conventions d’appel ou de retour normales.  
  
 Un appel à `setjmp` enregistre l’environnement de pile actuel dans `env`. Un appel ultérieur à `longjmp` restaure l’environnement enregistré et redonne le contrôle au point situé de suite après l’appel `setjmp` correspondant. Toutes les variables (à l’exception des variables de Registre) accessibles à la routine recevant le contrôle contiennent les valeurs qu’elles possédaient au moment où `longjmp` a été appelé.  
  
 Il n’est pas possible d’utiliser `setjmp` pour passer du code natif à du code managé.  
  
 **Remarque** `setjmp` et `longjmp` ne prennent pas en charge la sémantique d’objet C++. Dans les programmes C++, utilisez le mécanisme de gestion des exceptions C++.  
  
 Pour plus d’informations, consultez [Utilisation de setjmp et longjmp](../../cpp/using-setjmp-longjmp.md).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`setjmp`|\<setjmp.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [_fpreset](../../c-runtime-library/reference/fpreset.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de processus et d’environnement](../../c-runtime-library/process-and-environment-control.md)   
 [longjmp](../../c-runtime-library/reference/longjmp.md)   
 [_setjmp3](../../c-runtime-library/setjmp3.md)