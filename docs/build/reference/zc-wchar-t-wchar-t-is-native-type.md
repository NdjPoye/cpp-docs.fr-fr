---
title: "/Zc:wchar_t (wchar_t est un type natif) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.TreatWChar_tAsBuiltInType"
  - "VC.Project.VCCLCompilerTool.TreatWChar_tAsBuiltInType"
  - "/Zc:wchar_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc (option du compilateur C++)"
  - "conformité des options du compilateur"
  - "wchar_t (type)"
  - "Zc (option du compilateur C++)"
  - "-Zc (option du compilateur C++)"
ms.assetid: b0de5a84-da72-4e5a-9a4e-541099f939e0
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:wchar_t (wchar_t est un type natif)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Analysez `wchar_t` en tant que type intégré selon la norme C\+\+.  Par défaut, **\/Zc:wchar\_t** est activé.  
  
## Syntaxe  
  
```  
/Zc:wchar_t[-]  
```  
  
## Notes  
 Si **\/Zc:wchar\_t** est activé, `wchar_t` est mappé au type natif spécifique à Microsoft `__wchar_t`.  Si **\/Zc:wchar\_t\-** \(avec un signe moins\) est spécifié, `wchar_t` est mappé à `typedef` pour `unsigned short`.  \(Dans Visual C\+\+ 6.0 et les versions antérieures, `wchar_t` n'a pas été implémenté en tant que type intégré mais a été déclaré dans wchar.h en tant que `typedef` pour `unsigned short`.\) Nous déconseillons **\/Zc:wchar\_t\-**, car la norme C\+\+ nécessite que `wchar_t` soit un type intégré.  L'utilisation de la version `typedef` peut entraîner des problèmes de portabilité.  Si vous effectuez une mise à niveau à partir de versions antérieures de Visual C\+\+ et si vous constatez l'erreur du compilateur [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md), car le code essaie de convertir implicitement `wchar_t` en `unsigned short`, nous vous recommandons de modifier le code pour corriger cette erreur, au lieu de définir **\/Zc:wchar\_t\-**.  
  
 Microsoft implémente `wchar_t` en tant que valeur non signée de deux octets.  Pour plus d'informations sur `wchar_t`, consultez [Plages de types de données](../../cpp/data-type-ranges.md) et [Types fondamentaux](../../cpp/fundamental-types-cpp.md).  
  
 Si vous écrivez un nouveau code qui doit interagir avec du code plus ancien toujours basé sur la version `typedef` de `wchar_t`, vous pouvez fournir des surcharges pour les variantes `unsigned short` et `__wchar_t` de `wchar_t`, afin que votre code puisse être lié au code compilé avec **\/Zc:wchar\_t** ou au code compilé sans lui.  Sinon, vous devez fournir deux builds différentes de la bibliothèque \(l'une avec et l'autre sans l'activation de **\/Zc:wchar\_t**\).  Même dans ce cas, nous vous recommandons de générer le code plus ancien à l'aide du compilateur que vous utilisez pour compiler le nouveau code.  Ne mélangez jamais les binaires compilés avec des compilateurs distincts.  
  
 Lorsque **\/Zc:wchar\_t** est spécifié, les symboles **\_WCHAR\_T\_DEFINED** et **\_NATIVE\_WCHAR\_T\_DEFINED** sont définis.  Pour plus d'informations, voir [Macros prédéfinies](../../preprocessor/predefined-macros.md).  
  
 Si votre code utilise les fonctions globales COM du compilateur, car **\/Zc:wchar\_t** est désormais activé par défaut, nous vous recommandons de remplacer les références explicites à comsupp.lib \(à partir du [pragma comment](../../preprocessor/comment-c-cpp.md) ou sur la ligne de commande\) par omsuppw.lib ou comsuppwd.lib.  \(Si vous devez compiler avec **\/Zc:wchar\_t\-**, utilisez comsupp.lib.\) Si vous incluez le fichier d'en\-tête comdef.h, la bibliothèque appropriée est automatiquement spécifiée.  Pour plus d'informations sur la prise en charge du compilateur COM, consultez [Prise en charge COM du compilateur](../../cpp/compiler-com-support.md).  
  
 Le type `wchar_t` n'est pas pris en charge lorsque vous compilez du code C.  Pour plus d'informations sur les problèmes de conformité avec Visual C\+\+, consultez [Comportement non standard](../../cpp/nonstandard-behavior.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, voir [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Dans le volet gauche, développez **Propriétés de configuration**, **C\/C\+\+**, puis sélectionnez **Langage**.  
  
3.  Modifiez la propriété **Traitement de WChar\_t en tant que type intégré**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.TreatWChar_tAsBuiltInType%2A>.  
  
## Voir aussi  
 [\/Zc \(Conformité\)](../../build/reference/zc-conformance.md)