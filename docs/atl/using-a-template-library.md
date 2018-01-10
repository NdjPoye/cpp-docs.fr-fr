---
title: "À l’aide d’une bibliothèque de modèles (ATL) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: template libraries
ms.assetid: 5e80ec6e-a61c-41ce-b34b-9a6252c46265
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5232d2169ae9442a945b48ba141a609003611a90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-a-template-library"></a>À l’aide d’une bibliothèque de modèles
Un modèle est un peu comme une macro. Comme avec une macro, appel d’un modèle provoque son développement (avec une substitution de paramètres appropriée) au code que vous avez écrit. Toutefois, un modèle va plus loin que cette option pour autoriser la création de nouvelles classes basées sur les types que vous passez en tant que paramètres. Ces nouvelles classes implémentent les méthodes de type sécurisé d’effectuer l’opération exprimée dans votre code de modèle.  
  
 Bibliothèques de modèles tels que ATL diffèrent des bibliothèques de classes C++ traditionnels dans la mesure où ils sont généralement fournies uniquement en tant que code source (ou en tant que code source avec un peu, prise en charge du moment de l’exécution) et ne sont pas par nature obligatoirement hiérarchiques par nature. Au lieu de la dérivation d’une classe pour obtenir les fonctionnalités souhaitées, vous instanciez une classe à partir d’un modèle.  
  
## <a name="see-also"></a>Voir aussi  
 [Introduction à ATL](../atl/introduction-to-atl.md)

