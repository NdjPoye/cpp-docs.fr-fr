---
title: "R6024 d’erreur d’exécution C | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6024
dev_langs:
- C++
helpviewer_keywords:
- R6024
ms.assetid: 0fb11c0f-9b81-4cab-81bd-4785742946a5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 98d52a7d143a1c65caee3fe68902e3a25b3a5f4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="c-runtime-error-r6024"></a>R6024 d’erreur d’exécution C
pas assez d’espace pour la table _onexit/atexit  
  
> [!NOTE]
>  Si vous rencontrez ce message d’erreur lors de l’exécution d’une application, l’application a été arrêtée, car il a un problème de mémoire interne. Cette erreur est généralement dû à une condition de mémoire, ou rarement, à un bogue dans le programme ou par l’altération des bibliothèques Visual C++ qu’il utilise.  
>   
>  Vous pouvez essayer de suivre les étapes ci-après pour corriger cette erreur :  
>   
>  -   Fermez les autres applications en cours d’exécution ou redémarrer votre ordinateur pour libérer la mémoire.  
> -   Utilisez le **applications et fonctionnalités** ou **programmes et fonctionnalités** page dans le **le panneau de configuration** pour réparer ou réinstaller le programme.  
> -   Utilisez le **applications et fonctionnalités** ou **programmes et fonctionnalités** page dans le **le panneau de configuration** pour réparer ou réinstaller toutes les copies de Microsoft Visual C++ Redistributable.  
> -   Vérifiez **mise à jour Windows** dans les **le panneau de configuration** pour les mises à jour logicielles.  
> -   Recherchez une version mise à jour de l’application. Si le problème persiste, contactez le fournisseur de l’application.  
  
 **Informations pour les programmeurs**  
  
 Cette erreur se produit, car il y avait pas de mémoire disponible pour le `_onexit` ou `atexit` (fonction). Cette erreur est due à une condition de mémoire insuffisante. Vous pouvez envisager d’allocation des tampons au démarrage de l’application pour faciliter l’enregistrement des données de l’utilisateur et pour effectuer une nouvelle application de sortie dans des conditions de mémoire insuffisante.