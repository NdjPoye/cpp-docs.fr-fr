---
title: "Erreur d’exécution C R6002 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6002
dev_langs:
- C++
helpviewer_keywords:
- R6002
ms.assetid: 8fbbe65a-9c43-459e-8342-e1f6d1cef7d0
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: e9b50be6f1fd646f45ea1530c78e652f38b09c90
ms.lasthandoff: 02/24/2017

---
# <a name="c-runtime-error-r6002"></a>Erreur d’exécution C R6002
prise en charge à virgule flottante non chargée  
  
 La bibliothèque à virgule flottante nécessaire n’était pas liée.  
  
> [!NOTE]
>  Si vous rencontrez ce message d’erreur lors de l’exécution d’une application, l’application a été arrêtée car il a un problème interne. Il existe plusieurs raisons possibles de cette erreur, mais souvent, elle est provoquée par un défaut dans le code de l’application, ou en essayant d’exécuter une application qui n’a pas été générée pour le processeur de votre ordinateur particulier.  
>   
>  Vous pouvez essayer de suivre les étapes ci-après pour corriger cette erreur :  
>   
>  -   Utilisez le **applications et fonctionnalités** ou **programmes et fonctionnalités** page dans le **le panneau de configuration** pour réparer ou réinstaller le programme.  
> -   Vérifiez **mise à jour Windows** dans les **le panneau de configuration** pour les mises à jour logicielles.  
> -   Recherchez une version mise à jour de l’application. Si le problème persiste, contactez le fournisseur de l’application.  
  
 **Informations pour les programmeurs**  
  
 Cette erreur peut se produire dans votre application lors de la bibliothèque à virgule flottante n’était pas liée. Recherchez une de ces causes :  
  
-   Une chaîne de format pour un `printf_s` ou `scanf_s` fonction contenait une spécification de format à virgule flottante et le programme ne contenait pas toutes les valeurs à virgule flottante ou les variables. Pour résoudre ce problème, utilisez un argument à virgule flottante pour qu’elles correspondent à la spécification de format à virgule flottante, ou procédez à une assignation à virgule flottante ailleurs dans le programme. Ce support en virgule flottante à charger.  
  
-   Le compilateur réduit la taille d’un programme en chargeant le support en virgule flottante uniquement lorsque cela est nécessaire. Le compilateur ne peut pas détecter les opérations à virgule flottante ou des spécifications de format à virgule flottante dans les chaînes de format, afin qu’il ne charge pas les routines à virgule flottante nécessaires. Pour résoudre ce problème, utilisez une spécification de format à virgule flottante et fournir un argument à virgule flottante ou procédez à une assignation à virgule flottante ailleurs dans le programme. Ce support en virgule flottante à charger.  
  
-   Dans un programme en plusieurs langues, une bibliothèque C a été spécifiée avant une bibliothèque FORTRAN lorsque le programme a été lié. Reliez et spécifiez la bibliothèque C dernière.
