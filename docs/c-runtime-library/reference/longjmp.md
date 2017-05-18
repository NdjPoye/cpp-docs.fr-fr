---
title: longjmp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- longjmp
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
- longjmp
dev_langs:
- C++
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
caps.latest.revision: 9
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: b5af03e83cc39c20fca310ba0c2377469c59ef38
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="longjmp"></a>longjmp
Restaure l’environnement de la pile et les paramètres régionaux d’exécution.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      void longjmp(  
   jmp_buf env,  
   int value   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `env`  
 Variable dans laquelle l’environnement est stocké.  
  
 *value*  
 Valeur à retourner à l’appel `setjmp`.  
  
## <a name="remarks"></a>Notes  
 La fonction `longjmp` restaure un environnement de pile et des paramètres régionaux d’exécution enregistrés dans `env` par `setjmp`. `setjmp` et `longjmp` permettent d’exécuter un `goto` non local ; ils sont généralement utilisés pour passer le contrôle d’exécution au code de gestion des erreurs ou le code récupération dans une routine appelée sans utiliser l’appel normal et les conventions de retour.  
  
 Quand `setjmp` est appelé, l’environnement de pile actuel est enregistré dans `env`. Un appel ultérieur à `longjmp` restaure l’environnement enregistré et retourne le contrôle au point qui suit immédiatement l’appel `setjmp` correspondant. L’exécution reprend comme si *value* avait simplement été retourné par l’appel `setjmp`. Les valeurs de toutes les variables (sauf les variables de Registre) qui sont accessibles à la routine qui reçoit le contrôle contiennent les valeurs qu’elles avaient quand `longjmp` a été appelé. Les valeurs des variables de Registre sont imprévisibles. La valeur retournée par `setjmp` doit être différente de zéro. Si *value* est passé en tant que 0, la valeur 1 est substituée dans le retour effectif.  
  
 Appelez `longjmp` avant que la fonction qui a appelé `setjmp` ne retourne le contrôle ; sinon, les résultats sont imprévisibles.  
  
 Respectez les restrictions suivantes quand vous utilisez `longjmp` :  
  
-   Ne partez pas du principe que les valeurs des variables de Registre restent les mêmes. Les valeurs des variables de Registre dans la routine qui appelle `setjmp` peuvent ne pas être restaurées aux valeurs appropriées après l’exécution de `longjmp`.  
  
-   N’utilisez pas `longjmp` pour transférer le contrôle hors d’une routine de gestion d’interruption, sauf si l’interruption est provoquée par une exception de virgule flottante. Dans ce cas, un programme peut retourner à partir d’un gestionnaire d’interruption par le biais de `longjmp` s’il réinitialise tout d’abord le package mathématique à virgule flottante en appelant `_fpreset`.  
  
     **Remarque** Soyez prudent quand vous utilisez `setjmp` et `longjmp` dans les programmes C++. Étant donné que ces fonctions ne prennent pas en charge la sémantique d’objet C++, il est préférable d’utiliser le mécanisme de gestion des exceptions C++.  
  
 Pour plus d’informations, consultez [Utilisation de setjmp et longjmp](../../cpp/using-setjmp-longjmp.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`longjmp`|\<setjmp.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [_fpreset](../../c-runtime-library/reference/fpreset.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de processus et d’environnement](../../c-runtime-library/process-and-environment-control.md)   
 [setjmp](../../c-runtime-library/reference/setjmp.md)
