---
title: Instanciation explicite | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- templates, instantiation
- explicit instantiation
- instantiation, explicit
ms.assetid: 8b0d4e32-45a6-49d5-8041-1ebdd674410e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e272652ecc82b65d0251194f17a746ddde58fcc1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="explicit-instantiation"></a>instanciation explicite
Vous pouvez utiliser l’instanciation explicite pour créer une instanciation d’une classe basée sur un modèle ou une fonction sans réellement l’utiliser dans votre code. Étant donné que cela est utile lorsque vous créez bibliothèque (.lib) les fichiers qui utilisent des modèles pour la distribution, les définitions de modèle non instancié ne sont pas placées dans des fichiers objets (.obj).  
  
 Ce code instancie explicitement `MyStack` pour `int` variables et six éléments :  
  
```cpp  
template class MyStack<int, 6>;  
```  
  
 Cette instruction crée une instanciation de `MyStack` sans réservation de stockage pour un objet. Code est généré pour tous les membres.  
  
 La ligne suivante instancie explicitement que la fonction membre de constructeur :  
  
```cpp  
template MyStack<int, 6>::MyStack( void );  
```  
  
 Vous pouvez instancier explicitement des modèles de fonction à l’aide d’un argument de type spécifique à nouveau les déclarer, comme indiqué dans l’exemple de [instanciation du modèle de fonction](../cpp/function-template-instantiation.md).  
  
 Vous pouvez utiliser le `extern` mot clé afin d’éviter l’instanciation automatique des membres. Exemple :  
  
```cpp  
extern template class MyStack<int, 6>;  
```  
  
 De même, vous pouvez marquer des membres spécifiques comme étant non instancié et externes :  
  
```cpp  
extern template MyStack<int, 6>::MyStack( void );  
```  
  
 Vous pouvez utiliser la `extern` (mot clé) pour conserver le compilateur de générer le même code d’instanciation dans plusieurs modules de l’objet. Vous devez instancier la fonction de modèle en utilisant les paramètres de modèle explicite spécifié au moins un module lié si la fonction est appelée, ou si vous obtenez une erreur de l’éditeur de liens lorsque le programme est généré.  
  
> [!NOTE]
>  Le `extern` mot clé dans la spécialisation s’applique uniquement aux fonctions membres définies en dehors du corps de la classe. Fonctions définies à l’intérieur de la déclaration de classe sont considérées comme des fonctions inline et sont toujours instanciées.  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles de fonctions](../cpp/function-templates.md)