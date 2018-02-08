---
title: "Constantes entières C | Microsoft Docs"
ms.custom: 
ms.date: 02/01/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- integer constants
ms.assetid: fcf6b83c-2038-49ec-91ca-3d5ca1f83037
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c23e90d235e1ad2a8cca577c5cfbf2be55b52b6
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
# <a name="c-integer-constants"></a>Constantes entières C

Une « constante Integer » est un nombre décimal (base 10), octal (base 8) ou hexadécimal (base 16) qui représente une valeur intégrale. Utilisez les constantes Integer pour représenter des valeurs entières qui ne peuvent pas être modifiées.

## <a name="syntax"></a>Syntaxe

*integer-constant* :  
&nbsp;&nbsp;*decimal-constant* *integer-suffix*<sub>opt</sub>  
&nbsp;&nbsp;*octal-constant* *integer-suffix*<sub>opt</sub>  
&nbsp;&nbsp;*hexadecimal-constant* *integer-suffix*<sub>opt</sub>  

*decimal-constant*:  
&nbsp;&nbsp;*nonzero-digit*  
&nbsp;&nbsp;*decimal-constant* *digit*  

*octal-constant* :  
&nbsp;&nbsp;**0**  
&nbsp;&nbsp;*octal-constant* *octal-digit*  

*hexadecimal-constant* :  
&nbsp;&nbsp;**0x**  *hexadecimal-digit*  
&nbsp;&nbsp;**0X**  *hexadecimal-digit*  
&nbsp;&nbsp;*hexadecimal-constant* *hexadecimal-digit*  

*nonzero-digit* : un des éléments suivants :  
&nbsp;&nbsp;**1 2 3 4 5 6 7 8 9**  

*octal-digit* : un des éléments suivants :  
&nbsp;&nbsp;**0 1 2 3 4 5 6 7**  

*hexadecimal-digit* : un des éléments suivants :  
&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**  
&nbsp;&nbsp;**a b c d e f**  
&nbsp;&nbsp;**A B C D E F**  
  
*integer-suffix* :  
&nbsp;&nbsp;*unsigned-suffix* *long-suffix*<sub>opt</sub>  
&nbsp;&nbsp;*long-suffix* *unsigned-suffix*<sub>opt</sub>  
&nbsp;&nbsp;*unsigned-suffix* *64-bit-integer-suffix*<sub>opt</sub>

*unsigned-suffix* : un des éléments suivants :  
&nbsp;&nbsp;**u U**  

*long-suffix* : un des éléments suivants :  
&nbsp;&nbsp;**l L**  
  
*64-bit-integer-suffix* : un des éléments &nbsp;&nbsp;**i64 I64**  

Les constantes Integer sont positives, à moins d’être précédées du signe moins (**-**). Le signe moins est interprété comme l'opérateur de négation arithmétique unaire. Pour plus d’informations sur cet opérateur, consultez [Opérateurs arithmétiques unaires](../c-language/unary-arithmetic-operators.md).

Si une constante Integer commence par **0x** ou **0X**, elle est hexadécimale. Si elle commence par le chiffre **0**, elle est octale. Sinon, elle est supposée être décimale.

Les lignes suivantes sont équivalentes :

```C
0x1C   /* = Hexadecimal representation for decimal 28 */
034    /* = Octal representation for decimal 28 */
```

Aucun espace blanc ne peut séparer les chiffres d'une constante Integer. Ces exemples illustrent des constantes décimales, octales et hexadécimales valides.

```C
/* Decimal Constants */
10
132
32179

/* Octal Constants */
012
0204
076663

/* Hexadecimal Constants */
0xa or 0xA
0x84
0x7dB3 or 0X7DB3
```

## <a name="see-also"></a>Voir aussi

[Constantes C](../c-language/c-constants.md)  
