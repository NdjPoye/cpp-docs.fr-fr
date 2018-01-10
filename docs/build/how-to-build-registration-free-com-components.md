---
title: "Comment : créer des composants COM sans inscription | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 018a3ba707f4c5cff73b5a5c54f82400a79a8d46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-build-registration-free-com-components"></a>Comment : générer des composants COM sans inscription
Les composants COM sans inscription sont des composants COM qui ont des manifestes générés dans les DLL.  
  
### <a name="to-build-manifests-into-com-components"></a>Pour générer des manifestes dans les composants COM  
  
1.  Ouvrez les pages de propriétés de projet pour le composant COM.  
  
2.  Développez le **propriétés de Configuration** nœud, puis développez le **outil manifeste** nœud.  
  
3.  Sélectionnez le **d’entrée et sortie** page de propriétés et définissez la **incorporer le manifeste** propriété égale à **Oui**.  
  
4.  Cliquez sur **OK**.  
  
5.  Générez la solution.  
  
## <a name="see-also"></a>Voir aussi  
 [Applications isolées](http://msdn.microsoft.com/library/aa375190)   
 [À propos des assemblys côte à côte](http://msdn.microsoft.com/library/ff951640)   
 [Guide pratique pour générer des applications isolées pour consommer des composants COM](../build/how-to-build-isolated-applications-to-consume-com-components.md)