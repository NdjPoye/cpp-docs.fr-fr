---
title: "/ Zc : trigraphs (Substitution de trigrammes) | Documents Microsoft"
ms.custom: 
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /Zc
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5fdc5fc6432335e964a05185b7647b152a57d8f4
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2018
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:, trigrammes (substitution de trigrammes) (C++)

Lorsque **/Zc : trigraphs** est spécifié, le compilateur remplace une séquence de caractères trigrammes à l’aide d’un caractère de ponctuation correspondant.

## <a name="syntax"></a>Syntaxe

> **/Zc:trigraphs**[**-**]  

## <a name="remarks"></a>Notes

A *trigraphe* se compose de deux points d’interrogation consécutifs (« ? ») suivi d’un troisième caractère unique. Le langage C standard prend en charge des trigraphes pour les fichiers sources qui utilisent un jeu de caractères qui ne contient-elle pas de représentation graphique pour certains caractères de ponctuation. Par exemple, lorsque les trigraphes sont activées, le compilateur remplace le « ?? = « trigraphe à l’aide du caractère « # ». Dans C ++ 14, trigrammes sont pris en charge comme dans C. La norme C ++ 17 supprime des trigraphes de langage C++. Dans le code C++, le **/Zc : trigraphs** option du compilateur Active la substitution des séquences de trigraphe par le caractère de ponctuation correspondant. **/Zc:trigraphs-** désactive la substitution de trigrammes.

Le **/Zc : trigraphs** option est désactivée par défaut, et que l’option n’est pas affectée quand le [/ permissive-](permissive-standards-conformance.md) option est spécifiée.

Pour une liste des trigrammes de C/C++ et un exemple qui montre comment utiliser les trigrammes, consultez [trigraphes](../../c-language/trigraphs.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio

1. Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).

1. Sélectionnez le **propriétés de Configuration** > **C/C++** > **ligne de commande** page de propriétés.

1. Modifier la **des Options supplémentaires** propriété à inclure **/Zc : trigraphs** ou **/Zc:trigraphs-** , puis **OK**.

## <a name="see-also"></a>Voir aussi

[/Zc (Conformité)](../../build/reference/zc-conformance.md)<br/>
[Trigraphes](../../c-language/trigraphs.md)<br/>
