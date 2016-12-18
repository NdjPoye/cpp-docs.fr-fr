---
title: "Recherche et tri | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.programs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "données (CRT), rechercher"
  - "rechercher (C++)"
  - "rechercher (C++), fonctions de recherche CRT"
  - "trier les données"
ms.assetid: 15e984f0-e155-46f5-8542-51c458792f54
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Recherche et tri
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez les fonctions suivantes pour la recherche et le tri.  
  
### Recherche et le tri des fonctions  
  
|Fonction|Recherche ou tri|Équivalent de .NET Framework|  
|--------------|----------------------|----------------------------------|  
|[bsearch](../c-runtime-library/reference/bsearch.md)|binary\_search|[\<caps:sentence id\="tgt8" sentenceid\="07fe7161f1b3ff07a50d0fdb13bc8ade" class\="tgtSentence"\>System::Collections::ArrayList::BinarySearch\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.binarysearch.aspx)|  
|[bsearch\_s](../c-runtime-library/reference/bsearch-s.md)|Une version plus sûre pour `bsearch`.|[\<caps:sentence id\="tgt10" sentenceid\="07fe7161f1b3ff07a50d0fdb13bc8ade" class\="tgtSentence"\>System::Collections::ArrayList::BinarySearch\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.binarysearch.aspx)|  
|[\_lfind](../c-runtime-library/reference/lfind.md)|Recherche séquentielle pour la valeur donnée|[\<caps:sentence id\="tgt13" sentenceid\="2b0a5c761626afecd7137a4eab4525f0" class\="tgtSentence"\>System::Collections::ArrayList::Contains\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.contains.aspx)|  
|[\_lfind\_s](../c-runtime-library/reference/lfind-s.md)|Une version plus sûre pour `_lfind`.|[\<caps:sentence id\="tgt15" sentenceid\="2b0a5c761626afecd7137a4eab4525f0" class\="tgtSentence"\>System::Collections::ArrayList::Contains\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.contains.aspx)|  
|[\_lsearch](../c-runtime-library/reference/lsearch.md)|La recherche séquentielle pour la valeur fournie, ajoutée pour ranger s'il est introuvable|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_lsearch\_s](../c-runtime-library/reference/lsearch-s.md)|Une version plus sûre pour `_lsearch`.|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[qsort](../c-runtime-library/reference/qsort.md)|Tri rapide|[\<caps:sentence id\="tgt27" sentenceid\="f0305a177c6971f2c3c37537da538229" class\="tgtSentence"\>System::Collections::ArrayList::Sort\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx)|  
|[qsort\_s](../c-runtime-library/reference/qsort-s.md)|Une version plus sûre pour `qsort`.|[\<caps:sentence id\="tgt29" sentenceid\="f0305a177c6971f2c3c37537da538229" class\="tgtSentence"\>System::Collections::ArrayList::Sort\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx)|  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)