---
title: "Proc&#233;dure pas &#224; pas&#160;: compilation d&#39;un programme&#160;C++ natif sur la ligne de commande | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "applications en ligne de commande (C++), natifs"
  - "compiler des programmes (C++)"
  - "code natif (C++)"
  - "Visual C++, code natif"
ms.assetid: b200cfd1-0440-498f-90ee-7ecf92492dc0
caps.latest.revision: 63
caps.handback.revision: 57
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: compilation d&#39;un programme&#160;C++ natif sur la ligne de commande
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ inclut un compilateur C\+\+ en ligne de commande que vous pouvez utiliser pour créer toutes sortes d’applications, depuis des applications console de base à des applications Windows universelles, des applications du Windows Store et des composants .NET.  
  
 Dans cette procédure pas à pas, vous créez un programme de console Visual C\+\+ élémentaire à l'aide d'un éditeur de texte, puis le compilez sur la ligne de commande.  
  
> [!NOTE]
>  Vous pouvez également utiliser l'environnement de développement intégré \(IDE\) de Visual Studio pour compiler les programmes Visual C\+\+. Pour plus d'informations, consultez [Procédure pas à pas : utilisation de projets et de solutions \(C\+\+\)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md).  
  
 Dans cette procédure pas à pas, vous pouvez utiliser votre propre programme Visual C\+\+ au lieu de taper le programme illustré, ou vous pouvez utiliser un exemple de code Visual C\+\+ provenant d'un autre article d'aide.  
  
## Composants requis  
 Pour effectuer cette procédure pas à pas, vous devez disposer d’une version de Visual Studio qui inclut les composants Visual C\+\+. Il est préférable de bien comprendre les concepts de base du langage C\+\+. Ces instructions supposent que vous utilisez Windows 10 et Visual Studio 2015, mais les instructions pour d’autres environnements et d’autres versions sont similaires.  
  
### Pour créer un fichier source Visual C\+\+ et le compiler depuis la ligne de commande  
  
1.  Ouvrez d’abord une **invite de commandes développeur**. Le compilateur Visual C\+\+ a besoin d’un environnement de commande spécial pour s’exécuter : vous ne pouvez pas donc utiliser une invite de commandes standard pour cette procédure pas à pas.  
  
     Dans le menu **Démarrer** de Windows, ouvrez **Toutes les applications**. Faites défiler vers le bas pour trouver et ouvrir le dossier **Visual Studio** de votre version de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], puis choisissez le raccourci **Invite de commandes développeur**.  
  
2.  Créez un répertoire pour stocker votre programme. Dans la fenêtre **Invite de commandes développeur**, entrez une commande `cd \` pour accéder à la racine du lecteur. Entrez une commande `md examples` qui permet de créer un répertoire pour l’exemple de code. Entrez ensuite une commande `cd examples` pour en faire votre répertoire de travail actuel. C’est là que se trouvera votre premier programme.  
  
3.  À l’invite de commandes, entrez **notepad hello.cpp**.  
  
     Lorsque vous êtes invité à créer un fichier, choisissez **Oui**. Une fenêtre du Bloc\-notes vide s’ouvre pour y entrer votre code.  
  
4.  Dans le Bloc\-notes, tapez les lignes suivantes :  
  
    ```cpp  
    #include <iostream> using namespace std; void main() { cout << "Hello, world, from Visual C++!" << endl; }  
    ```  
  
     Il s’agit d’un programme très simple qui écrit une seule ligne de texte sur l’écran, puis s’arrête. Pour minimiser les risques d’erreurs, copiez le code et collez\-le dans le Bloc\-notes.  
  
5.  Enregistrez votre travail. Dans le Bloc\-notes, dans le menu **Fichier**, choisissez **Enregistrer**.  
  
     Vous venez de créer un fichier source Visual C\+\+.  
  
6.  À l’invite de commandes, entrez `cl /EHsc hello.cpp` pour compiler votre programme.  
  
     Le compilateur cl.exe génère un fichier .obj qui contient le code compilé, puis exécute l’éditeur de liens pour créer un programme exécutable nommé hello.exe. Ce nom apparaît dans les lignes des informations de sortie affichées par le compilateur. La sortie du compilateur doit ressembler à ceci :  
  
    ```Output  
    Compilateur d’optimisation Microsoft (R) C/C++ version 19.00.23504 pour x86. Copyright (C) Microsoft Corporation.  Tous droits réservés. hello.cpp Microsoft (R) Incremental Linker Version 14.00.23504.0 Copyright (C) Microsoft Corporation.  Tous droits réservés. /out:hello.exe hello.obj  
    ```  
  
     S’il existe des erreurs, vérifiez votre code dans le Bloc\-notes pour vous assurer qu’il correspond à l’exemple. Après l’enregistrement de vos modifications, exécutez à nouveau la commande du compilateur.  Si la commande cl est introuvable, vérifiez que vous utilisez l’invite de commandes développeur et non pas une fenêtre de commande standard. S’il n’est pas déjà installé, vous devez également installer le composant Visual C\+\+ dans le programme d’installation de Visual Studio.  
  
7.  Pour exécuter le programme hello.exe, à l’invite de commandes, entrez `hello`.  
  
     Le programme affiche ce texte puis se ferme :  
  
    ```Output  
    Hello, world, from Visual C++!  
    ```  
  
     Félicitations \! Vous avez créé et compilé un programme en utilisant les outils de ligne de commande.  
  
## Étapes suivantes  
 Pour plus d’informations sur la façon d’ouvrir une fenêtre d’invite de commandes développeur pour utiliser les outils en ligne de commande, consultez [Définition du chemin d'accès et des variables d'environnement pour la génération à partir de la ligne de commande](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
 Des informations d'identification d'administrateur peuvent être nécessaires pour compiler le code de cette procédure pas à pas, selon la configuration et le système d'exploitation de l'ordinateur. Pour exécuter la fenêtre Invite de commandes développeur en tant qu’administrateur, cliquez avec le bouton droit pour ouvrir le menu contextuel de l’**Invite de commandes développeur**, puis choisissez **Exécuter en tant qu’administrateur**.  
  
 L’option de ligne de commande **\/EHsc** indique au compilateur d’activer la gestion des exceptions C\+\+. Pour plus d'informations, consultez [\/EH \(Modèle de gestion des exceptions\)](../build/reference/eh-exception-handling-model.md).  
  
## Voir aussi  
 [Visite guidée de Visual C\+\+](http://msdn.microsoft.com/fr-fr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)   
 [Génération de programmes C\/C\+\+](../build/building-c-cpp-programs.md)   
 [Options du compilateur](../build/reference/compiler-options.md)