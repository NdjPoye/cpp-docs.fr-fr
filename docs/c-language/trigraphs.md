---
title: "Trigraphes | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "? (symbole), trigraphe"
  - "?? (trigraphe)"
  - "??' (trigraphe)"
  - "??- (trigraphe)"
  - "??! (trigraphe)"
  - "??) (trigraphe)"
  - "??/ (trigraphe)"
  - "??< (trigraphe)"
  - "??= (trigraphe)"
  - "??> (trigraphe)"
  - "point d'interrogation, dans les trigraphes"
  - "trigraphes"
ms.assetid: 617f76ec-b8e8-4cfe-916c-4bc32cbd9aeb
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Trigraphes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le jeu de caractères source des programmes sources C est contenu dans le jeu de caractères ASCII de 7 bits, mais c'est un sur\-ensemble de l'ensemble de code invariant ISO 646\-1983.  Les séquences de trigraphe permettent d'écrire des programmes C en utilisant uniquement l'ensemble de codes invariant ISO \(organisation internationale de normalisation\).  Les trigraphes sont des séquences de trois caractères \(introduites par deux points d'interrogation consécutifs\) que le compilateur remplace par leurs caractères de ponctuation correspondants.  Vous pouvez utiliser des trigraphes dans les fichiers sources C avec un jeu de caractères qui ne contient pas de représentation graphique pour certains caractères de ponctuation.  
  
 Le tableau suivant indique les neuf séquences de trigraphe.  Dans un fichier source, toutes les occurrences des caractères de ponctuation de la première colonne sont remplacées par le caractère correspondant de la deuxième colonne.  
  
### Séquences de trigraphe  
  
|Trigraphe|Caractère de ponctuation|  
|---------------|------------------------------|  
|??\=|\#|  
|??\(|\[|  
|??\/|\\|  
|??\)|\]|  
|??'|^|  
|??\<|{|  
|??\!|&#124;|  
|??\>|}|  
|??\-|~|  
  
 Un trigraphe est toujours traité comme un caractère source unique.  La traduction des trigraphes a lieu dans la première [phase de traduction](../preprocessor/phases-of-translation.md), avant la reconnaissance des caractères d'échappement dans les littéraux de chaîne et des constantes de caractère.  Seuls les neuf trigraphes indiqués dans le tableau ci\-dessus sont identifiés.  Toutes les autres séquences de caractères restent inchangées.  
  
 La séquence d'échappement de caractère, **\\?**, évite que les séquences de caractères qui s'apparentent à un trigraphe ne soient mal interprétées. \(Pour plus d'informations sur les séquences d'échappement, consultez [Séquences d'échappement](../c-language/escape-sequences.md).\) Par exemple, si vous essayez d'imprimer la chaîne `What??!` avec cette instruction `printf`  
  
```  
printf( "What??!\n" );  
```  
  
 la chaîne imprimée est `What|` car `??!` est une séquence de trigraphe qui est remplacée par le caractère          `|` .  Entrez l'instruction comme suit pour imprimer correctement la chaîne :  
  
```  
printf( "What?\?!\n" );  
```  
  
 Dans cette instruction `printf`, un caractère d'échappement barre oblique inverse devant le deuxième point d'interrogation empêche d'interpréter `??!` comme un trigraphe, ce qui serait une mauvaise interprétation.  
  
## Voir aussi  
 [Identificateurs C](../c-language/c-identifiers.md)