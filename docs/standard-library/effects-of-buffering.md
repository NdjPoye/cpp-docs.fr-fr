---
title: "Effets de la mise en mémoire tampon | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- buffers, effects of buffering
- buffering, effects of
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 460bc234ed438a92328d49c3821079bfb688da21
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="effects-of-buffering"></a>Effets de la mise en mémoire tampon
L’exemple suivant montre les effets de la mise en mémoire tampon. Vous vous attendez peut-être à ce que le programme affiche `please wait`, en vous laissant patienter 5 secondes, avant de continuer. Toutefois, cela ne fonctionne pas nécessairement de cette façon, car la sortie est mise en mémoire tampon.  
  
```  
// effects_buffering.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <time.h>  
using namespace std;  
  
int main( )  
{  
   time_t tm = time( NULL ) + 5;  
   cout << "Please wait...";  
   while ( time( NULL ) < tm )  
      ;  
   cout << "\nAll done" << endl;  
}  
```  
  
 Pour que le programme fonctionne de manière logique, l’objet `cout` doit se vider lui-même quand le message s’affiche. Pour vider un objet `ostream` , envoyez-lui le manipulateur `flush` :  
  
```  
cout <<"Please wait..." <<flush;  
```  
  
 Cette étape vide la mémoire tampon, en s’assurant que le message s’affiche avant l’attente. Vous pouvez également utiliser le `endl` manipulateur, qui vide la mémoire tampon et génère un retour chariot-saut de ligne, ou vous pouvez utiliser la `cin` objet. Cet objet (avec les objets `cerr` ou `clog` ) est généralement lié à l’objet `cout` . Ainsi, toute utilisation de `cin` (ou des objets `cerr` ou `clog` ) entraîne le vidage de l’objet `cout` .  
  
## <a name="see-also"></a>Voir aussi  
 [Flux de sortie](../standard-library/output-streams.md)

