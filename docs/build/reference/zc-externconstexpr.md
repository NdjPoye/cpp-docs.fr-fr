---
title: /Zc:externConstexpr (activer les variables extern constexpr) | Documents Microsoft
ms.custom: 
ms.date: 02/28/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /Zc:externConstexpr
dev_langs:
- C++
helpviewer_keywords:
- -Zc:externConstexpr compiler option (C++)
- extern constexpr variables (C++)
ms.assetid: 4da5e33a-2e4d-4ed2-8616-bd8f43265c27
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6597bc96609ab051df56886ccc580516986f97ed
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2018
---
# <a name="zcexternconstexpr-enable-extern-constexpr-variables"></a>/Zc:externConstexpr (activer les variables extern constexpr)

Le **/Zc:externConstexpr** option du compilateur indique au compilateur de conforme à la norme C++ et autoriser une liaison externe pour `constexpr` variables. Par défaut, Visual Studio donne toujours un `constexpr` variable une liaison interne, même si vous spécifiez le `extern` (mot clé).

## <a name="syntax"></a>Syntaxe

> **/Zc:externConstexpr**[**-**]

## <a name="remarks"></a>Notes

Le **/Zc:externConstexpr** option du compilateur, le compilateur applique une liaison externe pour les variables déclarées à l’aide de `extern constexpr`. Dans les versions antérieures de Visual Studio et, par défaut ou si **/Zc:externConstexpr-** est spécifié, Visual Studio applique une liaison interne à `constexpr` même si de variables le `extern` mot clé est utilisé. Le **/Zc:externConstexpr** option est disponible à partir de 15,6 de mise à jour de Visual Studio 2017. et est désactivée par défaut. Le [/ permissive-](permissive-standards-conformance.md) option n’active pas **/Zc:externConstexpr**.

Si un fichier d’en-tête contient une variable déclarée `extern constexpr`, il doit être marqué [__declspec (selectany)](../../cpp/selectany.md) pour fusionner les déclarations en double dans une seule instance dans le fichier binaire lié. Sinon, vous pouvez voir les erreurs de l’éditeur de liens LNK2005, par exemple, les violations de la règle de définition unique.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Pour définir cette option de compilateur dans Visual Studio

1. Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).

1. Sélectionnez le **propriétés de Configuration** > **C/C++** > **ligne de commande** page de propriétés.

1. Ajouter **/Zc:externConstexpr** ou **/Zc:externConstexpr-** à la **des options supplémentaires :** volet.

## <a name="see-also"></a>Voir aussi

[/Zc (Conformité)](../../build/reference/zc-conformance.md)  
[auto, mot clé](../../cpp/auto-keyword.md)