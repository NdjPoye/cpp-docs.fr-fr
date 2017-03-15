---
title: "Proc&#233;dure pas &#224; pas&#160;: compilation d&#39;un programme&#160;C++/CLI sur la ligne de commande | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: cef41c88-faf9-439d-8423-25aa3f5674dd
caps.latest.revision: 11
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: compilation d&#39;un programme&#160;C++/CLI sur la ligne de commande
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez créer des programmes Visual C\+\+ qui ciblent le Common Language Runtime \(CLR\) et utilisent le .NET Framework, et vous pouvez les générer à partir de la ligne de commande.  Visual C\+\+ prend en charge le langage de programmation C\+\+\/CLI, qui possède des types et opérateurs supplémentaires pour cibler le modèle de programmation .NET.  Pour une introduction au langage C\+\+\/CLI, consultez [Langage C\+\+ pur : C\+\+\/CLI](http://msdn.microsoft.com/magazine/cc163681.aspx).  Pour obtenir des informations générales, consultez [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).  
  
 Dans cette procédure pas à pas, vous allez créer un programme C\+\+\/CLI élémentaire à l'aide d'un éditeur de texte, puis le compiler sur la ligne de commande.  \(Vous pouvez utiliser votre propre programme C\+\+\/CLI au lieu de taper le programme illustré, ou vous pouvez utiliser un exemple de code C\+\+\/CLI tiré d'un autre article d'aide.  Cette technique est utile pour générer et tester des petits modules qui ne contiennent pas d'éléments d'interface utilisateur\).  
  
> [!NOTE]
>  Vous pouvez également utiliser l'IDE de Visual Studio pour compiler les programmes C\+\+\/CLI.  Pour plus d'informations, consultez [Procédure pas à pas : compilation d'un programme C\+\+ qui cible le CLR dans Visual Studio](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md).  
  
## Composants requis  
 Vous devez posséder des notions de base du langage C\+\+.  
  
## Compilation d'un programme C\+\+\/CLI  
 La procédure suivante illustre la compilation d'une application de console C\+\+\/CLI qui utilise des classes .NET Framework.  
  
 Pour activer la compilation pour du code C\+\+\/CLI, vous devez utiliser l'option de compilateur [\/clr](../build/reference/clr-common-language-runtime-compilation.md).  Le compilateur Visual C\+\+ génère un fichier .exe qui contient du code MSIL \(ou du code mixte MSIL\/natif\) et le lie aux bibliothèques .NET Framework nécessaires.  
  
#### Pour compiler une application C\+\+\/CLI sur la ligne de commande  
  
1.  Ouvrez une fenêtre d'**invite de commandes développeur**.  \(Dans la fenêtre **Démarrer**, ouvrez **Applications**.  Ouvrez le dossier **Visual Studio Tools** sous votre version de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], puis choisissez le raccourci **Invite de commandes développeur**.\) Pour plus d'informations sur la façon d'ouvrir une fenêtre d'invite de commandes, consultez [Définition du chemin d'accès et des variables d'environnement pour la génération à partir de la ligne de commande](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
     Des informations d'identification d'administrateur peuvent être nécessaires pour compiler le code, selon la configuration et le système d'exploitation de l'ordinateur.  Pour exécuter la fenêtre d'invite de commandes en tant qu'administrateur, ouvrez le menu contextuel de l'**invite de commandes développeur**, puis choisissez **Exécuter en tant qu'administrateur**.  
  
2.  À l'invite de commandes, entrez **notepad basicclr.cpp**.  
  
     Lorsque vous êtes invité à créer un fichier, choisissez **Oui**.  
  
3.  Dans le Bloc\-notes, tapez les lignes suivantes :  
  
    ```  
    int main()  
    {  
        System::Console::WriteLine("This is a C++/CLI program.");  
    }  
    ```  
  
4.  Dans la barre de menus, choisissez **Fichier**, **Enregistrer**.  
  
     Vous venez de créer un fichier source Visual C\+\+ qui utilise une classe .NET Framework \(<xref:System.Console>\) dans l'espace de noms <xref:System>.  
  
5.  À l'invite de commandes, entrez **cl \/clr basicclr.cpp**.  Le compilateur cl.exe compile le code source en un fichier .obj qui contient du code MSIL, puis exécute l'éditeur de liens pour générer un programme exécutable nommé basicclr.exe.  
  
6.  Pour exécuter le programme basicclr.exe, à l'invite de commandes, entrez **basicclr**.  
  
     Le programme affiche ce texte puis se ferme :  
  
  **This is a C\+\+\/CLI program.**  
  
## Voir aussi  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/fr-fr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)   
 [Génération de programmes C\/C\+\+](../build/building-c-cpp-programs.md)   
 [Options du compilateur](../build/reference/compiler-options.md)