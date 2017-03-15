---
title: "Platform, default, and cli Namespaces  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "lang"
  - "cli"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lang namespace"
  - "cli namespace"
ms.assetid: 9d38bd1e-dc78-47d1-a84b-9b4683e52c9c
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Platform, default, and cli Namespaces  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un espace de noms qualifie les noms des éléments du langage afin que les noms n'entrent pas en conflit avec des noms sinon identiques ailleurs dans le code source.  Par exemple, une collision de nom risque d'empêcher le compilateur de reconnaître des [Mots clés contextuels](../windows/context-sensitive-keywords-cpp-component-extensions.md).  Les espaces de noms sont utilisés par le compilateur mais ne sont pas conservés dans l'assembly compilé.  
  
## Tous les runtimes  
 Visual C\+\+ offre un espace de noms par défaut pour votre projet lorsque vous créez le projet.  Vous pouvez renommer manuellement l'espace de noms, même si, dans [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], le nom du fichier de .winmd doit correspondre au nom de l'espace de noms racine.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Pour plus d'informations, consultez [Visibilité des espaces de noms et des types \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh969551.aspx).  
  
### Spécifications  
 Option du compilateur : **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Syntaxe**  
  
```  
using namespace cli;  
```  
  
 **Notes**  
  
 Le [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] prend en charge l'espace de nom `cli`.  Lors de la compilation avec **\/clr**, l'instruction `using` de la section Syntaxe est implicite.  
  
 Les fonctionnalités de langage suivantes se trouvent dans l'espace de noms `cli` :  
  
-   [Arrays](../windows/arrays-cpp-component-extensions.md)  
  
-   [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)  
  
-   [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)  
  
-   [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)  
  
### Spécifications  
 Option du compilateur : **\/clr**  
  
### Exemples  
 **Exemple**  
  
 L'exemple de code suivant montre qu'il est possible d'utiliser un symbole dans l'espace de noms `cli` comme symbole défini par l'utilisateur dans votre code.  Toutefois, une fois que vous l'avez fait, vous devez qualifier explicitement ou implicitement vos références à l'élément de langage `cli` du même nom.  
  
```  
// cli_namespace.cpp  
// compile with: /clr  
using namespace cli;  
int main() {  
   array<int> ^ MyArray = gcnew array<int>(100);  
   int array = 0;  
  
   array<int> ^ MyArray2 = gcnew array<int>(100);   // C2062  
  
   // OK  
   cli::array<int> ^ MyArray2 = gcnew cli::array<int>(100);  
   ::array<int> ^ MyArray3 = gcnew ::array<int>(100);  
}  
```  
  
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)