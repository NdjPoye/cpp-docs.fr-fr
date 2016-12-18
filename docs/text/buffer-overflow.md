---
title: "D&#233;passement de capacit&#233; du tampon | Microsoft Docs"
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
  - "dépassements de capacité du tampon (C++)"
  - "mémoires tampons (C++), tailles de caractères"
  - "MBCS (C++), dépassement de capacité du tampon"
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
caps.latest.revision: 8
caps.handback.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# D&#233;passement de capacit&#233; du tampon
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les différentes tailles de caractères peuvent poser problème lorsque des caractères sont placés dans le tampon.  Dans le code suivant, les caractères sont copiés d'une chaîne `sz` dans un tampon `rgch` :  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
    rgch[ cb++ ] = *sz++;  
```  
  
 La question qui se pose est la suivante : Le dernier octet copié est\-il un octet de tête ?  Le code suivant ne résout pas ce problème car il peut entraîner un dépassement de capacité du tampon :  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 L'appel `_mbccpy` essaie de copier le caractère, qu'il soit codé sur un ou deux octets.  Mais il ne tient pas compte du fait que le dernier caractère copié ne tient pas dans le tampon si le caractère est codé sur deux octets.  La solution correcte est :  
  
```  
cb = 0;  
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 Ce code teste le dépassement de capacité du tampon dans un test de boucle, en utilisant `_mbclen` pour tester la taille du caractère en cours vers lequel pointe `sz`.  En appelant la fonction `_mbsnbcpy`, vous pouvez remplacer le code dans la boucle `while` par une seule ligne de code.  Par exemple :  
  
```  
_mbsnbcpy( rgch, sz, sizeof( rgch ) );  
```  
  
## Voir aussi  
 [Conseils de programmation MBCS](../text/mbcs-programming-tips.md)