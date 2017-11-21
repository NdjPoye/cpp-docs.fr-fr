---
title: "Erreur d’exécution C R6025 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6025
dev_langs: C++
helpviewer_keywords: R6025
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 06fd7aa6458a3c7e89d80146ec20a0e3f7587b4b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="c-runtime-error-r6025"></a>Erreur d’exécution C R6025
appel de fonction virtuelle pure  
  
> [!NOTE]
>  Si vous rencontrez ce message d’erreur lors de l’exécution d’une application, l’application a été arrêtée, car il a un problème interne. La raison la plus courante de cette erreur est un bogue dans l’application ou d’une installation endommagée.  
>   
>  Vous pouvez essayer de suivre les étapes ci-après pour corriger cette erreur :  
>   
>  -   Utilisez le **applications et fonctionnalités** ou **programmes et fonctionnalités** page dans le **le panneau de configuration** pour réparer ou réinstaller le programme.  
> -   Vérifiez **mise à jour Windows** dans les **le panneau de configuration** pour les mises à jour logicielles.  
> -   Recherchez une version mise à jour de l’application. Si le problème persiste, contactez le fournisseur de l’application.  
  
 **Informations pour les programmeurs**  
  
 Aucun objet n’a été instancié pour gérer l’appel de fonction virtuelle pure.  
  
 Cette erreur est due en appelant une fonction virtuelle dans une classe de base abstraite via un pointeur qui est créé par un cast vers le type de la classe dérivée, mais est en fait un pointeur vers la classe de base. Cela peut se produire lors de la conversion d’un **void\***  vers un pointeur vers une classe lorsque le **void\***  a été créé pendant la construction de la classe de base.  
  
 Pour plus d’informations, consultez la [prise en charge Microsoft](http://go.microsoft.com/fwlink/?LinkId=75220) site Web.