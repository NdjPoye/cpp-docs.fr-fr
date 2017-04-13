---
title: Compilateur avertissement (niveau 3) C4635 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4635
dev_langs:
- C++
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: d4c85ca32903e20ea18a731872c25ee999b67f89
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4635"></a>Avertissement du compilateur (niveau 3) C4635
Cible de commentaire de document XML : code XML incorrect : raison  
  
 Le compilateur a détecté un problème avec les balises XML.  Corrigez le problème et recompilez.  
  
 L’exemple suivant génère l’avertissement C4635 :  
  
```  
// C4635.cpp  
// compile with: /doc /clr /W3 /c  
/// <summary>     
/// The contents of the folder have changed.  
/// <summary/>   // C4635  
  
// try the following line instead  
// /// </summary>  
public ref class Test {};  
```  
  
 Notez que la sortie de cet exemple indique : **La balise de fin 'member' ne correspond pas à la balise de début 'summary'.**  
  
 Le problème avec cet exemple est que la balise de fin pour \<résumé > est mal formée, et le compilateur ne la reconnaît pas comme la \<résumé > la balise de fin.  Le \<membre > est incorporée dans le fichier .xdc par le compilateur dans chaque compilation /doc.  Par conséquent, le problème ici est que la balise de fin \</Member >, ne correspond pas à la balise de début précédente traité par le compilateur (\<résumé >.
