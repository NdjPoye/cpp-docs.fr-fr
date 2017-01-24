---
title: "Probl&#232;mes courants lors de la cr&#233;ation d&#39;une version release | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "versions debug, différence par rapport aux versions release"
  - "allocateur de mémoire debug"
  - "déboguer (MFC), versions release"
  - "problèmes de présentation du tas"
  - "mémoire (C++), remplacements"
  - "MFC (C++), versions release"
  - "optimisation (C++), compilateur"
  - "pointeurs, perdus"
  - "projets (C++), configuration Debug"
  - "versions release, générer des applications"
  - "versions release, dépanner"
  - "pointeurs perdus"
  - "dépanner les versions release"
  - "dépanner Visual C++"
  - "génération de code inattendue"
ms.assetid: 73cbc1f9-3e33-472d-9880-39a8e9977b95
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Probl&#232;mes courants lors de la cr&#233;ation d&#39;une version release
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

En cours de développement, vous serez généralement amené à effectuer des générations et des tests à l'aide d'une version debug de votre projet.  Si vous générez ensuite votre application en vue de produire une version release, vous pouvez provoquer une violation d'accès.  
  
 La liste ci\-dessous montre les principales différences entre les versions debug et release \(non debug\).  D'autres différences existent, mais celles qui suivent sont les principales différences pouvant entraîner l'échec en version release d'une application qui fonctionne en version debug.  
  
-   [Présentation du tas](#_core_heap_layout)  
  
-   [Compilation](#_core_compilation)  
  
-   [Prise en charge du pointeur](#_core_pointer_support)  
  
-   [Optimisations](#_core_optimizations)  
  
 Consultez l'option de compilation [\/GZ \(Intercepter des erreurs de versions release dans les versions debug\)](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md) pour obtenir des informations sur la manière d'intercepter les erreurs des versions release dans les versions debug.  
  
##  <a name="_core_heap_layout"></a> Présentation du tas  
 La présentation du tas est à l'origine de 90 % environ des problèmes apparents quand une application fonctionne en version debug, mais pas en version release.  
  
 Lorsque vous générez votre projet pour la version debug, vous utilisez l'allocateur de mémoire debug.  Ceci signifie que toutes les allocations de mémoire sont entourées d'octets de garde.  Ces octets de garde détectent les remplacements de mémoire.  Dans la mesure où la présentation du tas diffère entre les versions release et debug, un remplacement de mémoire peut ne pas créer d'incidents dans une version debug, mais avoir des effets catastrophiques dans une version release.  
  
 Pour plus d'informations, consultez [Vérification des remplacements de mémoire](../../build/reference/checking-for-memory-overwrites.md) et [Utilisation de la version debug pour vérifier les remplacements de mémoire](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md).  
  
##  <a name="_core_compilation"></a> Compilation  
 Nombre de macros MFC et une grande partie de l'implémentation des MFC sont modifiées lors d'une génération destinée à produire une version release.  En particulier, la macro ASSERT se traduit par une chaîne nulle dans une version release, et le code contenu dans les instructions ASSERT n'est ainsi pas exécuté.  Pour plus d'informations, consultez [Examen des instructions ASSERT](../../build/reference/using-verify-instead-of-assert.md).  
  
 Certaines fonctions sont déclarées inline pour accélérer la vitesse d'exécution lors de la génération de la version release.  Les optimisations sont généralement activées dans une version release.  Un allocateur de mémoire différent est également utilisé.  
  
##  <a name="_core_pointer_support"></a> Prise en charge du pointeur  
 L'absence d'informations de débogage supprime la marge intérieure de votre application.  Dans une version release, les pointeurs perdus ont plus de chances de désigner une mémoire non initialisée que de référencer des informations de débogage.  
  
##  <a name="_core_optimizations"></a> Optimisations  
 Selon la nature de certains segments de code, le compilateur d'optimisation peut générer un code inattendu.  C'est la cause la moins probable des problèmes liés aux versions release, mais elle se manifeste quand même de temps à autre.  Pour une solution, consultez [Optimisation du code](../../build/reference/optimizing-your-code.md).  
  
## Voir aussi  
 [Versions release](../../build/reference/release-builds.md)   
 [Résolution de problèmes liés à la version release](../../build/reference/fixing-release-build-problems.md)