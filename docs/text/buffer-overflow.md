---
title: "Dépassements de mémoire tampon | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- buffers [C++], character sizes
- buffer overflows [C++]
- MBCS [C++], buffer overflow
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4bfad181ee7c6b702af87bc8ff0a49ccfb42cb65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="buffer-overflow"></a>Dépassement de capacité du tampon
Différentes tailles de caractères peut provoquer des problèmes lorsque vous placez des caractères dans une mémoire tampon. Prenons le code suivant, qui copie les caractères d’une chaîne, `sz`, dans une mémoire tampon, `rgch`:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
    rgch[ cb++ ] = *sz++;  
```  
  
 La question est : a été le dernier octet copié un octet de tête ? Les éléments suivants ne résout pas le problème, car il peut présenter un dépassement du tampon :  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 Le `_mbccpy` appel tente d’obtenir le résultat correct, copier le caractère, s’il s’agit de 1 ou 2 octets. Mais il ne prend pas en compte que le dernier caractère copié répondent pas forcément à la mémoire tampon si le caractère est égale à 2 octets. La solution correcte est :  
  
```  
cb = 0;  
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 Ce code teste le dépassement de capacité de mémoire tampon possible dans la boucle de test, à l’aide de `_mbclen` pour tester la taille du caractère en cours vers lequel pointé `sz`. En effectuant un appel à la `_mbsnbcpy` (fonction), vous pouvez remplacer le code dans le `while` boucle avec une seule ligne de code. Exemple :  
  
```  
_mbsnbcpy( rgch, sz, sizeof( rgch ) );  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Conseils de programmation MBCS](../text/mbcs-programming-tips.md)