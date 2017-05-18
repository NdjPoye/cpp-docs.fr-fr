---
title: Fichiers de sortie binaires | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- I/O [C++], binary output files
- files [C++], binary output files
- binary data, binary output files
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 8968a47f9d957aa0873b5db78909a6b4ad66ea75
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="binary-output-files"></a>Fichiers de sortie binaires
Les flux ont été conçus à l’origine pour le texte, par conséquent, le mode de sortie par défaut est le mode texte. En mode texte, le caractère de saut de ligne (10 hexadécimal) se développe en un retour chariot (16 bits uniquement). L’extension peut entraîner des problèmes, comme le montre ce qui suit :  
  
```  
// binary_output_files.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
int main( )  
{  
    ofstream os( "test.dat" );  
    os.write( (char *) iarray, sizeof( iarray ) );  
}  
```  
  
 Vous pouvez vous attendre à ce que ce programme génère la séquence d’octets {99, 0, 10, 0} ; au lieu de cela, il génère {99, 0, 13, 10, 0}, ce qui entraîne des problèmes pour un programme qui attend une entrée binaire. Si vous avez besoin d’une véritable sortie binaire, dans laquelle les caractères sont écrits sans traduction, vous pouvez spécifier une sortie binaire à l’aide de l’argument openmode du constructeur [ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) :  
  
```  
// binary_output_files2.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
  
int main()  
{  
   ofstream ofs ( "test.dat", ios_base::binary );  
  
   // Exactly 8 bytes written  
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );   
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Flux de sortie](../standard-library/output-streams.md)


