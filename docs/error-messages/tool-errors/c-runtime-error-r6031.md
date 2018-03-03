---
title: "Erreur d’exécution C R6031 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6031
dev_langs:
- C++
helpviewer_keywords:
- R6031
ms.assetid: 805d4cd1-cb2f-43fe-87e6-e7bd5b7329c5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 260c316ad43ce39a60cb7e54137a363754c1ddf7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="c-runtime-error-r6031"></a>Erreur d’exécution C R6031
Tentative d’initialisation de la bibliothèque CRT plusieurs fois. Cela indique un bogue dans votre application.  
  
> [!NOTE]
>  Si vous rencontrez ce message d’erreur lors de l’exécution d’une application, l’application a été arrêtée, car il a un problème interne. Cela peut être dû bogue dans l’application ou par un bogue dans un module complémentaire ou d’une extension de l’application utilise.  
>   
>  Vous pouvez essayer de suivre les étapes ci-après pour corriger cette erreur :  
>   
>  -   Utilisez le **applications et fonctionnalités** ou **programmes et fonctionnalités** page dans le **le panneau de configuration** pour réparer ou réinstaller le programme.  
> -   Utilisez le **applications et fonctionnalités** ou **programmes et fonctionnalités** page dans le **le panneau de configuration** pour supprimer, réparer ou réinstaller tous les programmes d’un module complémentaire ou l’extension utilisées par l’application.  
> -   Vérifiez **mise à jour Windows** dans les **le panneau de configuration** pour les mises à jour logicielles.  
> -   Recherchez une version mise à jour de l’application. Si le problème persiste, contactez le fournisseur de l’application.  
  
 **Informations pour les programmeurs**  
  
 Ce diagnostic indique que des instructions MSIL s’exécutaient lors du verrouillage du chargeur. Pour plus d’informations, consultez [l’initialisation d’assemblys mixtes](../../dotnet/initialization-of-mixed-assemblies.md).