---
title: "-Zc : wchar_t (wchar_t est un Type natif) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.TreatWChar_tAsBuiltInType
- VC.Project.VCCLCompilerTool.TreatWChar_tAsBuiltInType
- /Zc:wchar_t
dev_langs:
- C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- wchar_t type
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: b0de5a84-da72-4e5a-9a4e-541099f939e0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3375e39120fdc8f2b0d8d5502aa6def997511ff5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="zcwchart-wchart-is-native-type"></a>/Zc:wchar_t (wchar_t est un type natif)
Analysez `wchar_t` en tant que type intégré selon la norme C++. Par défaut, **/Zc :** se trouve sur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/Zc:wchar_t[-]  
```  
  
## <a name="remarks"></a>Notes  
 Si **/Zc :** est activé, `wchar_t` mappé au type natif spécifique à Microsoft `__wchar_t`. Si **/Zc:wchar_t-** (avec un signe moins) est spécifié, `wchar_t` est mappé à un `typedef` pour `unsigned short`. (Dans Visual C++ 6.0 et les versions antérieures, `wchar_t` n'a pas été implémenté en tant que type intégré mais a été déclaré dans wchar.h en tant que `typedef` pour `unsigned short`.) Nous ne recommandons pas **/Zc:wchar_t-** , car la norme C++ requiert que `wchar_t` être un type intégré. L'utilisation de la version `typedef` peut entraîner des problèmes de portabilité. Si vous mettez à niveau des versions antérieures de Visual C++ et rencontrez l’erreur du compilateur [l’erreur C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) parce que le code tente de convertir implicitement un `wchar_t` à `unsigned short`, nous vous recommandons de modifier le code pour corriger cette erreur, à la place paramètre **/Zc:wchar_t-**.  
  
 Microsoft implémente `wchar_t` en tant que valeur non signée de deux octets. Pour plus d’informations sur `wchar_t`, consultez [plages de types de données](../../cpp/data-type-ranges.md) et [Types fondamentaux](../../cpp/fundamental-types-cpp.md).  
  
 Si vous écrivez un nouveau code qui doit interagir avec l’ancien code qui utilise toujours le `typedef` version de `wchar_t`, vous pouvez fournir des surcharges pour les deux le `unsigned short` et `__wchar_t` variantes de `wchar_t`, de sorte que votre code peut être lié à le code compilé avec **/Zc :** ou code compilé sans lui. Sinon, vous devez fournir deux builds différentes de la bibliothèque, une avec et sans **/Zc :** activé. Même dans ce cas, nous vous recommandons de générer le code plus ancien à l'aide du compilateur que vous utilisez pour compiler le nouveau code. Ne mélangez jamais les binaires compilés avec des compilateurs distincts.  
  
 Lorsque **/Zc :** est spécifié, **_WCHAR_T_DEFINED** et **_NATIVE_WCHAR_T_DEFINED** symboles qui sont définis. Pour plus d'informations, consultez [Predefined Macros](../../preprocessor/predefined-macros.md).  
  
 Si votre code utilise les fonctions globales COM du compilateur, car **/Zc :** est maintenant sur par défaut, nous vous recommandons de modifier les références explicites à comsupp.lib le [commentaire pragma](../../preprocessor/comment-c-cpp.md) ou sur la commande ligne : par omsuppw.lib ou comsuppwd.lib. (Si vous devez compiler avec **/Zc:wchar_t-**, utilisez comsupp.lib.) Si vous incluez le fichier d'en-tête comdef.h, la bibliothèque appropriée est automatiquement spécifiée. Pour plus d’informations sur la prise en charge COM du compilateur, consultez [Support COM du compilateur](../../cpp/compiler-com-support.md).  
  
 Le type `wchar_t` n'est pas pris en charge lorsque vous compilez du code C. Pour plus d’informations sur les problèmes de conformité avec Visual C++, consultez [comportement non standard](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Dans le volet gauche, développez **propriétés de Configuration**, **C/C++**, puis sélectionnez **langue**.  
  
3.  Modifier la **traitement de wchar_t en tant que Type intégré** propriété.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.TreatWChar_tAsBuiltInType%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [/Zc (conformité)](../../build/reference/zc-conformance.md)