---
title: "Mécanismes de base des attributs | Documents Microsoft"
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
- attributes [C++], inserting in code
- attributes [C++], about attributes
ms.assetid: dc2069c3-b9f3-4a72-965c-4e5208ce8e34
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 99771e798e4957de5ff69601a5d3494e5fcacc35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="basic-mechanics-of-attributes"></a>Mécanismes de base des attributs
Il existe trois manières d’insérer des attributs dans votre projet. Tout d’abord, vous pouvez les insérer manuellement dans votre code source. Ensuite, vous pouvez insérer dans votre projet à l’aide de la grille des propriétés d’un objet. Enfin, vous pouvez insérer à l’aide des Assistants différents. Pour plus d’informations sur l’utilisation de la fenêtre Propriétés et les divers Assistants, consultez [création et gestion de projets Visual C++](../ide/creating-and-managing-visual-cpp-projects.md).  
  
 Comme précédemment, lorsque le projet est généré, le compilateur analyse chaque fichier source C++, produit un fichier objet. Toutefois, lorsque le compilateur rencontre un attribut, il est analysé et sa syntaxe est vérifiée. Le compilateur appelle ensuite dynamiquement un fournisseur d’attributs pour insérer du code ou apporter d’autres modifications à la compilation. L’implémentation du fournisseur diffère selon le type d’attribut. Par exemple, les attributs liés à ATL sont implémentées par Atlprov.dll.  
  
 L’illustration suivante montre la relation entre le compilateur et le fournisseur d’attributs.  
  
 ![Communication des attributs de composant](../windows/media/vccompattrcomm.gif "vcCompAttrComm")  
  
> [!NOTE]
>  Utilisation d’attributs ne modifie pas le contenu du fichier source. Le seul moment où que le code généré d’attribut est visible est pendant les sessions de débogage. En outre, pour chaque fichier source dans le projet, vous pouvez générer un fichier texte qui affiche les résultats de la substitution de l’attribut. Pour plus d’informations sur cette procédure, consultez [/Fx (fusionner le Code injecté)](../build/reference/fx-merge-injected-code.md) et [débogage de Code injecté](/visualstudio/debugger/how-to-debug-injected-code).  
  
 Comme la plupart des constructions C++, les attributs ont un ensemble de caractéristiques qui définit leur utilisation appropriée. Cela est appelé le contexte de l’attribut et est traité dans la table de contexte d’attribut pour chaque rubrique de référence d’attribut. Par exemple, le [coclasse](../windows/coclass.md) attribut peut uniquement être appliqué à une classe existante ou une structure, par opposition à la [cpp_quote](../windows/cpp-quote.md) attribut, qui peut être inséré n’importe où dans un fichier source C++.  
  
## <a name="see-also"></a>Voir aussi  
 [Concepts](../windows/attributed-programming-concepts.md)