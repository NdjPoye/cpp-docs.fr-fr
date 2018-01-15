---
title: "Compatibilité internationale | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- globalization [C++], character sets
- strings [C++], international enabling
- localization [C++], character sets
- MBCS [C++], enabling
- Unicode [C++], enabling
ms.assetid: b077f4ca-5865-40ef-a46e-d9e4d686ef21
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ce0210546dafd354d0d62225c97df8b36a8d84e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="international-enabling"></a>Compatibilité internationale
Code plus classique de C et C++ émet des hypothèses sur la manipulation de caractère et de chaîne qui ne fonctionnent pas correctement dans les applications internationales. MFC et la bibliothèque Runtime prend en charge Unicode ou MBCS, il reste encore à faire. Pour vous guider, cette section explique la signification de « compatibilité internationale » dans Visual C++ :  
  
-   Unicode et MBCS sont activés au moyen des types de données portables dans les listes de paramètres de fonction MFC et les types de retour. Ces types sont définis de façon conditionnelle de la façon appropriée, selon que votre compilation définit le symbole **_UNICODE** ou le symbole **_MBCS** (ce qui signifie DBCS). Différentes variantes des bibliothèques MFC sont automatiquement liés à votre application, en fonction de ces deux symboles définit votre build.  
  
-   Code de bibliothèque de classes utilise des fonctions runtime portables et autres moyens pour garantir le comportement Unicode ou MBCS.  
  
-   Vous devez toujours gérer certains types de tâches d’internationalisation dans votre code :  
  
    -   Utilisez les mêmes fonctions runtime portables qui rendent MFC portable sous les deux environnements.  
  
    -   Rendre les chaînes littérales et caractères portables sous les deux environnements, à l’aide de la **_T** (macro). Pour plus d’informations, consultez [des mappages de texte générique dans Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
    -   Prenez des précautions lors de l’analyse de chaînes sous MBCS. Ces précautions ne sont pas nécessaires sous Unicode. Pour plus d’informations, consultez [conseils de programmation MBCS](../text/mbcs-programming-tips.md).  
  
    -   Faites attention lorsque vous mélangez ANSI (8 bits) et les caractères Unicode (16 bits) dans votre application. Il est possible d’utiliser des caractères ANSI dans certaines parties de votre programme et des caractères Unicode dans d’autres, mais vous ne pouvez pas les mélanger dans la même chaîne.  
  
    -   Ne pas coder en dur les chaînes de votre application. Au lieu de cela, vérifiez les ressources STRINGTABLE en les ajoutant au fichier .rc de l’application. Votre application peut ensuite être localisée sans nécessiter de recompilation ou modifications du code source. Pour plus d’informations sur les ressources STRINGTABLE, consultez [éditeur de chaînes](../windows/string-editor.md).  
  
> [!NOTE]
>  Les jeux de caractères européens et MBCS utilisent des caractères, tels que les lettres accentuées, avec des codes de caractères supérieurs à 0 x 80. Étant donné que la plupart du code utilise des caractères signés, ces caractères supérieurs à 0 x 80 sont étendue avec un signe lorsqu’elle est convertie en `int`. Il s’agit d’un problème pour l’indexation de tableau, car les caractères de signe étendu, qui est négatif, les index en dehors du tableau. Les langues qui utilisent MBCS, telles que le japonais, sont également uniques. Car un caractère peut se composer de 1 ou 2 octets, vous devez toujours manipuler les deux octets en même temps.  
  
## <a name="see-also"></a>Voir aussi  
 [Unicode et MBCS](../text/unicode-and-mbcs.md)   
 [Stratégies d’internationalisation](../text/internationalization-strategies.md)