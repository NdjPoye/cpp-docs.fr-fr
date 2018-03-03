---
title: "/Zc:sizedDealloc (activer des fonctions de Global désallocation dimensionnée) | Documents Microsoft"
ms.custom: 
ms.date: 12/13/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sizedDealloc
- /Zc:sizedDealloc
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- sizedDealloc
- Enable Global Sized Deallocation Functions
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 3a73ace0-4d36-420a-b699-0ca6fc0dd134
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1343c037f87aee609de2b082cb87f7f1f2832221
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="zcsizeddealloc-enable-global-sized-deallocation-functions"></a>/Zc:sizedDealloc (activer des fonctions de Global désallocation dimensionnée)  
Le `/Zc:sizedDealloc` option du compilateur indique au compilateur d’appeler préférence global `operator delete` ou `operator delete[]` des fonctions ayant un deuxième paramètre de type `size_t` lorsque la taille de l’objet est disponible. Ces fonctions peuvent utiliser le `size_t` paramètre pour optimiser les performances d’annulateur d’allocation.   
  
## <a name="syntax"></a>Syntaxe  
`/Zc:sizedDealloc`[`-`\]  
  
## <a name="remarks"></a>Notes  
  
Dans la norme C ++ 11, vous pouvez définir les fonctions membres statiques `operator delete` et `operator delete[]` qui accepte un deuxième, `size_t` paramètre. En général, ceux-ci sont utilisés en association avec [new, opérateur](../../cpp/new-operator-cpp.md) fonctions pour mettre en œuvre plus efficace des allocateurs et annulateurs d’allocation de l’objet. Toutefois, C ++ 11 n’ont pas défini un ensemble équivalent de fonctions de désallocation dans une portée globale. Dans C ++ 11, désallocation global des fonctions ayant un deuxième paramètre de type `size_t` sont considérés comme des fonctions de positionnement delete. Elles doivent être appelées explicitement en passant un argument de taille.  
  
La norme C ++ 14 modifie le comportement du compilateur. Lorsque vous définissez global `operator delete` et `operator delete[]` qui accepte un deuxième paramètre de type `size_t`, s’il préfère que le compilateur d’appeler ces fonctions lorsque les versions des membres de portée ne sont pas appelées et la taille de l’objet est disponible. Le compilateur passe l’argument de taille implicitement. Les versions de l’argument unique sont appelées lorsque le compilateur ne peut pas déterminer la taille de l’objet désalloué. Dans le cas contraire, les règles habituelles pour choisir la version de la fonction de désallocation à appeler s’appliquent toujours. Les appels aux fonctions globales peuvent être spécifiées explicitement en ajoutant au début de l’opérateur de résolution de portée (`::`) à l’appel de fonction de désallocation.  
  
Par défaut, Visual C++ depuis Visual Studio 2015 implémente ce comportement par défaut 14 C ++. Vous pouvez spécifier explicitement ceci en définissant le `/Zc:sizedDealloc` option du compilateur. Il s’agit d’une nouveauté modification. Utilisez le `/Zc:sizedDealloc-` option pour conserver l’ancien comportement, par exemple, lorsque votre code définit les opérateurs de supprimer la sélection élective qui utilisent un deuxième paramètre de type `size_t`. Les implémentations de bibliothèque Visual Studio par défaut des fonctions de désallocation global dont le deuxième paramètre de type `size_t` appeler les versions de paramètre unique. Si votre code fournit le seul paramètre unique global de l’opérateur delete et l’opérateur delete [], les implémentations de bibliothèque par défaut des fonctions de désallocation dimensionnée global appellent vos fonctions globales.  
  
Pour plus d’informations sur les problèmes de conformité dans Visual C++, consultez [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).  
  
## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
2.  À partir de la **Configurations** menu déroulant, choisissez **toutes les Configurations**.  
3.  Sélectionnez le **propriétés de Configuration**, **C/C++**, **ligne de commande** page de propriétés.  
4.  Modifier la **des Options supplémentaires** propriété à inclure `/Zc:sizedDealloc` ou `/Zc:sizedDealloc-` , puis **OK**.  
  
## <a name="see-also"></a>Voir aussi  
[Options du compilateur](../../build/reference/compiler-options.md)  
[Définition des options du compilateur](../../build/reference/setting-compiler-options.md)  
[/Zc (conformité)](../../build/reference/zc-conformance.md)  
