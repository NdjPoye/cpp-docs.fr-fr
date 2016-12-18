---
title: "Utilisation de dllimport et dllexport dans les classes C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes (C++), déclarer"
  - "classes (C++), exportable et héritage"
  - "déclarations (C++), de classes"
  - "déclarer des classes"
  - "dllexport (attribut) (C++)"
  - "dllexport (attribut) (C++), classes"
  - "dllimport (attribut) (C++), classes"
  - "classes exportables (C++)"
  - "exporter des classes"
  - "héritage (C++), classes exportables"
ms.assetid: 8d7d1303-b9e9-47ca-96cc-67bf444a08a9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de dllimport et dllexport dans les classes C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Vous pouvez déclarer des classes C\+\+ avec l'attribut **dllimport** ou `dllexport`.  Ces formes impliquent que toute la classe soit importée ou exportée.  Les classes exportées de cette façon sont appelées des classes exportables.  
  
 L'exemple suivant définit une classe exportable.  Toutes ses fonctions membres et données statiques sont exportées :  
  
```  
#define DllExport   __declspec( dllexport )  
  
class DllExport C {  
   int i;  
   virtual int func( void ) { return 1; }  
};  
```  
  
 Notez que l'utilisation explicite des attributs **dllimport** et `dllexport` sur les membres d'une classe exportable est interdite.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bdllexportclasses"></a> Classes de dllexport  
 Lorsque vous déclarez une classe `dllexport`, toutes ses fonctions membres et membres de données statiques sont exportés.  Vous devez fournir les définitions de tous ces membres dans le même programme.  Sinon, une erreur d'éditeur de liens est générée.  La seule exception à cette règle s'applique aux fonctions virtuelles pures, pour lesquelles vous n'avez pas besoin de fournir de définitions explicites.  Toutefois, étant donné qu'un destructeur d'une classe abstraite est toujours appelé par le destructeur de la classe de base, les destructeurs virtuels purs doivent toujours fournir une définition.  Notez que ces règles sont identiques pour les classes non exportables.  
  
 Si vous exportez des données de classe de type ou des fonctions qui retournent des classes, veillez à exporter la classe.  
  
##  <a name="_pluslang_dllexport_classesdllexportclasses"></a> Classes de dllimport  
 Lorsque vous déclarez une classe **dllimport**, toutes ses fonctions membres et membres de données statiques sont importés.  Contrairement au comportement de **dllimport** et `dllexport` sur les types sans classe, les membres de données statiques ne peuvent pas spécifier une définition dans le même programme que celui où une classe **dllimport** est définie.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2binheritanceandexportableclasses"></a> Héritage et classes exportables  
 Toutes les classes de base d'une classe exportable doivent être exportées.  Sinon, un avertissement du compilateur est généré.  De plus, tous les membres accessibles qui sont également des classes doivent être exportables.  Cette règle permet à une classe `dllexport` d'hériter d'une classe **dllimport** et à une classe **dllimport** d'hériter d'une classe `dllexport` \(bien que ce dernier cas soit déconseillé\).  En règle générale, tout ce qui est accessible au client de la DLL \(conformément aux règles d'accès C\+\+\) doit faire partie de l'interface exportable.  Cela inclut les données membres privées référencées dans les fonctions inline.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bselectivememberimportexport"></a> Importation\/exportation de membres sélectifs  
 Étant donné que les fonctions membres et les données statiques appartenant à une classe ont implicitement la liaison externe, vous pouvez les déclarer avec l'attribut **dllimport** ou `dllexport`, à moins que la classe entière ne soit exportée.  Si la classe entière est importée ou exportée, la déclaration explicite des fonctions et données membres comme **dllimport** ou `dllexport` est interdite.  Si vous déclarez un membre de données statique dans une définition de classe comme `dllexport`, une définition doit apparaître quelque part dans le même programme \(comme avec une liaison externe qui n'est pas de classe\).  
  
 De même, vous pouvez déclarer des fonctions membres avec les attributs **dllimport** ou `dllexport`.  Dans ce cas, vous devez fournir une définition `dllexport` à un emplacement du même programme.  
  
 Il est intéressant de noter plusieurs aspects importants concernant l'importation et l'exportation de membres sélectifs :  
  
-   L'importation\/exportation de membres sélectifs permet principalement de fournir une version de l'interface de classe exportée qui est plus restrictive ; autrement dit, une version pour laquelle vous pouvez concevoir une DLL qui expose moins de fonctionnalités publiques et privées que ne le permet le langage.  Cela permet également d'affiner l'interface exportable : lorsque vous savez que le client, par définition, ne peut pas accéder à certaines données privées, vous n'avez pas besoin d'exporter la classe entière.  
  
-   Si vous exportez une seule fonction virtuelle d'une classe, vous devez toutes les exporter ou fournir au moins les versions que le client peut utiliser directement.  
  
-   Si vous avez une classe dans laquelle vous utilisez l'importation\/exportation de membres sélectifs avec des fonctions virtuelles, les fonctions doivent être dans l'interface exportable ou définies inline \(visibles par le client\).  
  
-   Si vous définissez un membre comme `dllexport` mais que vous ne l'incluez pas dans la définition de classe, une erreur de compilation est générée.  Vous devez définir le membre dans l'en\-tête de classe.  
  
-   Bien que la définition des membres de classe comme **dllimport** ou `dllexport` soit autorisée, vous ne pouvez pas remplacer l'interface spécifiée dans la définition de classe.  
  
-   Si vous définissez une fonction membre dans un emplacement autre que le corps de la définition de classe dans laquelle vous l'avez déclarée, un avertissement est généré si la fonction est définie comme `dllexport` ou **dllimport** \(si cette définition diffère de celle spécifiée dans la déclaration de classe\).  
  
### FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)