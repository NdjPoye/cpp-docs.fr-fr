---
title: "R6017 d’erreur d’exécution C | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6017
dev_langs:
- C++
helpviewer_keywords:
- R6017
ms.assetid: df3ec5f5-6771-4648-ba06-0e26c6a1cc6a
caps.latest.revision: 7
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 903d440dbedbe704ae28be643337619ca1e09c69
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="c-runtime-error-r6017"></a>R6017 d’erreur d’exécution C
Erreur de verrouillage multithread inattendue  
  
> [!NOTE]
>  Si vous rencontrez ce message d’erreur lors de l’exécution d’une application, l’application a été arrêtée car il a un problème interne. Il existe plusieurs raisons possibles de cette erreur, mais souvent, elle est provoquée par un défaut dans le code de l’application.  
>   
>  Vous pouvez essayer de suivre les étapes ci-après pour corriger cette erreur :  
>   
>  -   Utilisez le **applications et fonctionnalités** ou **programmes et fonctionnalités** page dans le **le panneau de configuration** pour réparer ou réinstaller le programme.  
> -   Vérifiez **mise à jour Windows** dans les **le panneau de configuration** pour les mises à jour logicielles.  
> -   Recherchez une version mise à jour de l’application. Si le problème persiste, contactez le fournisseur de l’application.  
  
 **Informations pour les programmeurs**  
  
 Le processus a reçu une erreur inattendue en essayant d’accéder à un verrou multithread d’exécution C sur une ressource système. Cette erreur se produit généralement quand le processus modifie par inadvertance les données de segment de mémoire du runtime. Toutefois, elle peut également être due à une erreur interne dans la bibliothèque runtime ou le code du système d’exploitation.  
  
 Pour résoudre ce problème, recherchez les bogues de corruption des tas dans votre code. Pour plus d’informations et d’exemples, consultez [détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details). Ensuite, vérifiez que vous utilisez les derniers redistribuables pour votre déploiement d’application. Pour plus d’informations, consultez [déploiement dans Visual C++](../../ide/deployment-in-visual-cpp.md).
