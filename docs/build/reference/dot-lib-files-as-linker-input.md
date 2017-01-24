---
title: ".Fichiers&#160;.lib en tant qu&#39;entr&#233;e de l&#39;&#201;diteur de liens | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.AdditionalDependencies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .lib"
  - "fichiers COFF, bibliothèques d'importation"
  - "bibliothèques par défaut (C++)"
  - "bibliothèques par défaut (C++), sortie de l'éditeur de liens"
  - "valeurs par défaut (C++), bibliothèques"
  - "bibliothèques d'importation, fichiers de l'éditeur de liens"
  - "bibliothèques (C++), .lib (fichiers en tant qu'entrée de l'éditeur de liens)"
  - "liaison (C++), bibliothèques OMF"
  - "bibliothèques OMF"
ms.assetid: dc5d2b1c-2487-41fa-aa71-ad1e0647958b
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .Fichiers&#160;.lib en tant qu&#39;entr&#233;e de l&#39;&#201;diteur de liens
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LINK accepte les bibliothèques standard COFF et les bibliothèques d'importation COFF, dont l'extension est en général .lib.  Les bibliothèques standard contiennent des objets et sont créées par l'outil LIB.  Les bibliothèques d'importation contiennent des informations sur les exportations dans d'autres programmes et sont créées soit par LINK lorsqu'il génère un programme contenant des exportations, soit par l'outil LIB.  Pour obtenir des informations sur l'utilisation de LIB pour créer des bibliothèques standard ou des bibliothèques d'importation, consultez [Référence LIB](../../build/reference/lib-reference.md).  Pour plus d'informations sur l'utilisation de LINK pour créer une bibliothèque d'importation, consultez l'option [\/DLL](../../build/reference/dll-build-a-dll.md).  
  
 Une bibliothèque est spécifiée dans LINK soit comme argument 'Nom fichier', soit comme bibliothèque par défaut.  LINK résout les références externes en faisant d'abord des recherches dans les bibliothèques spécifiées sur la ligne de commande, puis dans les bibliothèques par défaut spécifiées avec l'option [\/DEFAULTLIB](../../build/reference/defaultlib-specify-default-library.md) et, enfin, dans les bibliothèques par défaut nommées dans les objets .obj.  Si un chemin d'accès est spécifié avec le nom de la bibliothèque, LINK recherche la bibliothèque dans ce répertoire.  Si aucun chemin d'accès n'est spécifié, LINK recherche d'abord dans le répertoire d'exécution de LINK, puis dans les répertoires spécifiés dans la variable d'environnement LIB.  
  
### Pour ajouter des fichiers .lib comme entrée dans l'éditeur de liens dans l'environnement de développement  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Entrée**.  
  
4.  Modifiez la propriété **Dépendances supplémentaires**.  
  
### Pour ajouter des fichiers .lib comme entrée dans l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalDependencies%2A>.  
  
## Exemple  
 L'exemple suivant montre comment générer et utiliser un fichier .lib :  
  
```  
// lib_link_input_1.cpp  
// compile with: /LD  
__declspec(dllexport) int Test() {  
   return 213;  
}  
```  
  
## Exemple  
 Ensuite :  
  
```  
// lib_link_input_2.cpp  
// compile with: /EHsc lib_link_input_1.lib  
__declspec(dllimport) int Test();  
#include <iostream>  
int main() {  
   std::cout << Test() << std::endl;  
}  
```  
  
  **213**   
## Voir aussi  
 [Fichiers d'entrée LINK](../../build/reference/link-input-files.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)