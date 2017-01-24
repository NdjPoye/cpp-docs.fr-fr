---
title: "Avertissement du compilateur (niveau 2) C4275 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4275"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4275"
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 2) C4275
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

interface non dll CléClasse 'identificateur' utilisée comme base d'une interface dll CléClasse 'identificateur'  
  
 Une classe exportée a été dérivée depuis une classe qui n'a pas été exportée.  
  
 Pour réduire le risque d'altération des données lors de l'exportation d'une classe avec [\_\_declspec \(dllexport\)](../../cpp/dllexport-dllimport.md), vérifiez les points suivants :  
  
-   Toutes vos données statiques sont accessibles par le biais de fonctions exportées à partir de la DLL.  
  
-   Aucune méthode inline de votre classe ne peut modifier de données statiques.  
  
-   Aucune méthode inline de votre classe n'utilise des fonctions CRT, ou d'autres fonctions de bibliothèque utilisent des données statiques.  
  
-   Aucune fonction de classe inline n'utilise des fonctions CRT ou d'autres fonctions de bibliothèque permettant, par exemple, d'accéder aux données statiques.  
  
-   Aucune méthode de votre classe \(indépendamment de la fonctionnalité inline\) ne peut utiliser de types dont l'instanciation dans les fichiers EXE et DLL comporte des différences au niveau des données statiques.  
  
 Vous pouvez éviter d'exporter des classes en configurant une DLL qui définit une classe avec des fonctions virtuelles, et des fonctions que vous pouvez appeler pour instancier et supprimer des objets de ce type.  Il vous suffit ensuite d'appeler les fonctions virtuelles sur ce type.  
  
 Pour plus d'informations sur l'exportation de modèles, consultez [http:\/\/support.microsoft.com\/default.aspx?scid\=KB;EN\-US;168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).  
  
 L'erreur C4275 peut être ignorée dans Visual C\+\+ si vous dérivez d'un type dans la bibliothèque C\+\+ standard et compilez une version Debug \(**\/MTd**\) et si le message d'erreur du compilateur fait référence à \_Container\_base.  
  
```  
// C4275.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275  
```