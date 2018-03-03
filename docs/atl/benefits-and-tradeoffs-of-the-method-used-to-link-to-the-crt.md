---
title: "Avantages et limitations de la méthode utilisée pour le lien vers la bibliothèque CRT | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 244415a947918a836e8c4c67dbd18758ec40393c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt"></a>Avantages et limitations de la méthode utilisée pour le lien vers la bibliothèque CRT
Votre projet peut lier de manière dynamique ou statique. Le tableau ci-dessous présente les avantages et inconvénients dans le choix de la méthode à utiliser.  
  
|Méthode|Avantage|Compromis|  
|------------|-------------|--------------|  
|Liaison statique à la bibliothèque CRT<br /><br /> (**De la bibliothèque Runtime** la valeur **monothread**)|La DLL CRT n’est pas requis sur le système où est exécutée l’image.|Environ 25 Ko de code de démarrage est ajouté à votre image, augmenter sa taille.|  
|Liaison dynamique à la bibliothèque CRT<br /><br /> (**De la bibliothèque Runtime** la valeur **multithread**)|Votre image ne nécessite pas le code de démarrage du CRT, par conséquent, il est beaucoup plus petite.|La DLL CRT doit être sur le système de l’image en cours d’exécution.|  
  
 La rubrique [au CRT dans votre projet ATL](../atl/linking-to-the-crt-in-your-atl-project.md) explique comment sélectionner le mode de liaison vers la bibliothèque CRT.  
  
## <a name="see-also"></a>Voir aussi  
 [Programmation avec ATL et le Code d’exécution C](../atl/programming-with-atl-and-c-run-time-code.md)   
 [DLL et le comportement de la bibliothèque d’exécution Visual C++](../build/run-time-library-behavior.md)   
 [Fonctionnalités de bibliothèque CRT](../c-runtime-library/crt-library-features.md)

