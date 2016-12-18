---
title: "nullptr | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "nullptr_cpp"
  - "nullptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nullptr (mot clé) (C++)"
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# nullptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Désigne une constante de pointeur null du type `std::nullptr_t`, qui peut être convertie en tout type pointeur brut.  Bien que vous puissiez utiliser le mot clé `nullptr` sans inclure aucun en\-tête, si votre code utilise le type `std::nullptr_t`, vous devez le définir en incluant l'en\-tête `<cstddef>`.  
  
> [!NOTE]
>  Le mot clé `nullptr` est aussi défini dans C\+\+\/CLI pour les applications en code managé ; il n'est pas interchangeable avec le mot clé C\+\+ de norme ISO.  Si votre code est susceptible d'être compilé à l'aide de l'option du compilateur [\/clr](../build/reference/clr-common-language-runtime-compilation.md), qui cible le code managé, utilisez `__nullptr` sur toute ligne de code où vous devez vous assurer que le compilateur utilise l'interprétation C\+\+ native.  Pour plus d'informations, consultez [nullptr](../windows/nullptr-cpp-component-extensions.md).  
  
## Notes  
 Évitez d'utiliser `NULL` ou zéro \(`0`\) comme constante de pointeur null ; `nullptr` est moins vulnérable aux risques d'utilisation incorrecte et fonctionne mieux dans la plupart des situations.  Par exemple, étant donné `func(std::pair<const char *, double>)`, l'appel à `func(std::make_pair(NULL, 3.14))` provoque une erreur du compilateur.  Étant donné que la macro NULL s'étend à `0`, l'appel `std::make_pair(0, 3.14)` retourne `std::pair<int, double>`, qui n'est pas convertible au type de paramètre `std::pair<const char *, double>` de func\(\).  L'appel à `func(std::make_pair(nullptr, 3.14))` entraîne une compilation correcte, car `std::make_pair(nullptr, 3.14)` retourne `std::pair<std::nullptr_t, double>`, qui peut être convertie en `std::pair<const char *, double>`.  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)