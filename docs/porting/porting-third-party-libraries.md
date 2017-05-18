---
title: "Portage de bibliothèques tierces | Microsoft Docs"
ms.custom: 
ms.date: 01/10/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- 3rd-party libraries
- vspkg
ms.assetid: b055ed20-8a9e-45b2-ac2a-e3d94271c009
caps.latest.revision: 0
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 8630a5c0b97b85e0dc75e8b470974bb7d223a511
ms.openlocfilehash: 1d85010b6068d52d8522875a3c47561ad777d345
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---

# <a name="porting-third-party-libraries"></a>Portage de bibliothèques tierces

Quand vous mettez à niveau un projet vers la version actuelle de Visual C++, vous devez également mettre à niveau toutes les bibliothèques qu’il utilise, afin que la bibliothèque et votre projet soient générés avec les mêmes version et configuration du compilateur. (Pour plus d’informations, consultez [Vue d’ensemble des problèmes de mise à niveau potentiels](overview-of-potential-upgrade-issues-visual-cpp.md)). 

## <a name="introducing-vcpkg"></a>Présentation de vcpkg
Dans le passé, la recherche et la mise à niveau de bibliothèques tierces représentaient parfois une tâche loin d’être futile. Pour faciliter l’acquisition et la régénération de bibliothèques open source tierces C++, l’équipe Visual C++ a créé un outil en ligne de commande appelé l’**outil d’empaquetage VC++** ou **vcpkg**. Vcpkg comporte un catalogue de nombreuses bibliothèques open source C++ populaires dans lequel vous pouvez effectuer des recherches. Vous pouvez installer n’importe quelle bibliothèque dans le catalogue directement à partir de la ligne de commande vcpkg. Quand vous installez une bibliothèque, Vcpkg crée une arborescence de répertoires sur votre ordinateur et ajoute les fichiers .h, .lib et binaires à ce dossier. Vous pouvez utiliser ce dossier dans votre ligne de commande de compilation, ou l’intégrer à Visual Studio 2015 ou version ultérieure à l’aide de la commande vcpkg integrate install. Après avoir intégré un emplacement de bibliothèque, Visual Studio peut le trouver et l’ajouter à n’importe quel projet que vous créez. Pour employer une bibliothèque, utilisez #include, et Visual Studio ajoute automatiquement le chemin d’accès au fichier .lib dans les paramètres du projet et copie la dll dans votre dossier de solution.

## <a name="acquisition-and-usage"></a>Acquisition et utilisation

Vous pouvez télécharger vcpkg à partir de [dépôt GitHub vcpkg][vcpkg](https://github.com/Microsoft/vcpkg/).

 - Pour rechercher une bibliothèque dans le catalogue : vcpkg search <LibName>
 - Pour acquérir une bibliothèque (par exemple, Boost) : vcpkg install boost
 - Pour répertorier les bibliothèques qui sont actuellement installées : vcpkg list

Le billet de blog [Vcpkg: a tool to acquire and build C++ open source libraries on Windows](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) explique le fonctionnement de vcpkg et donne la liste des bibliothèques prises en charge. Cette liste est actualisée chaque semaine.

## <a name="reporting-issues"></a>Problèmes liés aux rapports
Si votre bibliothèque ne figure pas dans le catalogue vcpkg, vous pouvez signaler un problème sur le [dépôt GitHub](https://github.com/Microsoft/vcpkg/issues) où la communauté et l’équipe Visual C++ peuvent le voir et éventuellement créer le fichier de port pour cette bibliothèque.

Pour les bibliothèques tierces propriétaires (non-open source), nous vous conseillons de contacter le fournisseur de la bibliothèque. Toutefois, nous aimerions connaître les bibliothèques propriétaires que vous utilisez et qui vous bloquent. Indiquez-nous celle dont vous dépendez (vous pouvez nous contacter à l’adresse vcupgrade@microsoft.com).

  
## <a name="see-also"></a>Voir aussi  
 [Guide du portage et de la mise à niveau de Visual C++](visual-cpp-porting-and-upgrading-guide.md)

