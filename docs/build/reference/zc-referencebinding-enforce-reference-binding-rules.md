---
title: "/Zc:referenceBinding (appliquer les règles de liaison aux référence) | Documents Microsoft"
ms.custom: 
ms.date: 12/13/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- referenceBinding
- /Zc:referenceBinding
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- referenceBinding
- Enforce reference binding rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 0c6cfaac-9c2a-41a3-aa94-64ca8ef261fc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0d3d352394b61f95e083a2e6e6f0d888fe210b37
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/Zc:referenceBinding (appliquer les règles de liaison aux référence)
Lorsque le **/Zc:referenceBinding** est spécifiée, le compilateur n’autorise pas une référence non const lvalue à lier à une variable temporaire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/Zc:referenceBinding[-]  
```  
  
## <a name="remarks"></a>Notes  
Si **/Zc:referenceBinding** est spécifié, le compilateur suit la section 8.5.3 de la norme C ++ 11 et n’autorise pas les expressions qui lient un type défini par l’utilisateur temporaire vers une référence non const lvalue. Par défaut, ou si **/Zc:referenceBinding-** est spécifié, le compilateur autorise ces expressions comme une extension Microsoft, mais un avertissement de niveau 4. Pour la sécurité du code, la portabilité et de la conformité, nous vous recommandons d’utiliser **/Zc:referenceBinding**. Le [/ permissive-](permissive-standards-conformance.md) option du compilateur définit implicitement cette option, mais elle peut être substituée à l’aide de **/Zc:referenceBinding-**.  
  
## <a name="example"></a>Exemple  
  
Cet exemple montre l’extension Microsoft qui permet à une valeur temporaire d’un type défini par l’utilisateur être lié à une référence non const lvalue.
```cpp  
// zcreferencebinding.cpp
struct S {
};

void f(S&) {
}

S g() {
    return S{};
}

void main() {
    S& s = g();         // warning C4239 at /W4
    const S& cs = g();  // okay, bound to const ref
    f(g());             // Extension: error C2664 only if /Zc:referenceBinding
}
```  
  
Pour plus d’informations sur les problèmes de conformité dans Visual C++, consultez [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le **C/C++** dossier.  
  
3.  Sélectionnez le **ligne de commande** page de propriétés.  
  
4.  Modifier la **des Options supplémentaires** propriété à inclure **/Zc:referenceBinding** , puis **OK**.  
  
## <a name="see-also"></a>Voir aussi  
[Options du compilateur](../../build/reference/compiler-options.md)   
[Définition des Options du compilateur](../../build/reference/setting-compiler-options.md)   
[/Zc (Conformité)](../../build/reference/zc-conformance.md)