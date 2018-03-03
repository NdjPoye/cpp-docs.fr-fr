---
title: Compilateur avertissement (niveau 3) C4635 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4635
dev_langs:
- C++
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 16b6a19618afeed952cfa594961a0e4ccb777d26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4635"></a>Avertissement du compilateur (niveau 3) C4635
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
  
 Le problème avec cet exemple est que la balise de fin pour \<Résumé > est mal formée, et le compilateur ne la reconnaît pas comme la \<Résumé > balise de fin.  Le \<membre > est incorporée dans le fichier .xdc par le compilateur dans chaque compilation /doc.  Par conséquent, le problème ici est que la balise de fin \</Member >, ne correspond pas à la balise de début précédente traité par le compilateur (\<Résumé >.