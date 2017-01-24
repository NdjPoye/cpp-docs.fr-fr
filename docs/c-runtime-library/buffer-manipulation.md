---
title: "Manipulation de la m&#233;moire tampon | Microsoft Docs"
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
  - "c.memory"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "mémoires tampons"
  - "mémoires tampons, routines de manipulation"
ms.assetid: 164f4860-ce66-412c-8291-396fbd70f03e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Manipulation de la m&#233;moire tampon
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez ces routines pour travailler avec des zones de mémoire sur une base octet par octet.  
  
### Routines de Mémoire tampon\-\)  
  
|Routine|Utilisez|Équivalent de .NET Framework|  
|-------------|--------------|----------------------------------|  
|[\_memccpy](../c-runtime-library/reference/memccpy.md)|Les caractères de copie d'un tampon vers une autre que le caractère donné ou le nombre spécifié de caractères a été copiés|[System::Buffer::BlockCopy](https://msdn.microsoft.com/en-us/library/system.buffer.blockcopy.aspx), [System::String::Copy](https://msdn.microsoft.com/en-us/library/system.string.copy.aspx)|  
|[memchr, wmemchr](../c-runtime-library/reference/memchr-wmemchr.md)|Pointeur de retour à la première occurrence, sur le nombre spécifié de caractères, des caractères donnés dans la mémoire tampon|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[memcmp, wmemcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|Compare a spécifié le nombre de caractères de deux mémoires tampons|[System::String::Compare](https://msdn.microsoft.com/en-us/library/system.string.compare.aspx), [System::String::Equals](https://msdn.microsoft.com/en-us/library/system.string.equals.aspx)|  
|[memcpy, wmemcpy](../c-runtime-library/reference/memcpy-wmemcpy.md), [memcpy\_s, wmemcpy\_s](../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)|La copie a spécifié le nombre de caractères d'un tampon vers une autre|[System::Buffer::BlockCopy](https://msdn.microsoft.com/en-us/library/system.buffer.blockcopy.aspx), [System::String::Copy](https://msdn.microsoft.com/en-us/library/system.string.copy.aspx)|  
|[\_memicmp, \_memicmp\_l](../c-runtime-library/reference/memicmp-memicmp-l.md)|Compare un nombre de caractères spécifié de deux mémoires tampons sans tenir compte de la casse|[System::String::Compare](https://msdn.microsoft.com/en-us/library/system.string.compare.aspx), [System::String::Equals](https://msdn.microsoft.com/en-us/library/system.string.equals.aspx)|  
|[memmove, wmemmove](../c-runtime-library/reference/memmove-wmemmove.md),[memmove\_s, wmemmove\_s](../c-runtime-library/reference/memmove-s-wmemmove-s.md)|Copie un nombre spécifié de caractères d'un tampon vers une autre|[\<caps:sentence id\="tgt21" sentenceid\="3833f84fafc5c85a0cac972319a7142c" class\="tgtSentence"\>System::Buffer::BlockCopy\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.buffer.blockcopy.aspx)|  
|[memset, wmemset](../c-runtime-library/reference/memset-wmemset.md)|Utilisez le caractère donné pour initialiser le nombre spécifié d'octets dans la mémoire tampon|[\<caps:sentence id\="tgt23" sentenceid\="b681ccb0db940e3c31a14bf4b7e7aaf8" class\="tgtSentence"\>System::Buffer::SetByte\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.buffer.setbyte.aspx)|  
|[\_swab](../c-runtime-library/reference/swab.md)|Permute les octets de données et les enregistre à l'emplacement spécifié|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
  
 Lorsque les zones cible se chevauchent, seul `memmove` garantit  de copier la source complète correctement.  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)