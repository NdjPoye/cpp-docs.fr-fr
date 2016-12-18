---
title: "Assemblys de nom fort (signature d&#39;assembly) (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".NET Framework (C++), signature d'assembly"
  - "assemblys (C++)"
  - "assemblys (C++), signer"
  - "éditeur de liens (C++), signature d'assembly"
  - "signer des assemblys"
  - "assemblys avec nom fort (C++)"
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Assemblys de nom fort (signature d&#39;assembly) (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique comment signer un assembly, opération souvent désignée par l'expression donner un nom fort à votre assembly.  
  
## Remarques  
 Lors de l'utilisation de Visual C\+\+, utilisez les options de l'éditeur de liens pour signer votre assembly afin d'éviter tout problème lié aux attributs CLR de signature d'assembly :  
  
-   <xref:System.Reflection.AssemblyDelaySignAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyFileAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyNameAttribute>  
  
 L'utilisation d'attributs n'est pas conseillée car le nom de la clé est visible dans les métadonnées de l'assembly, ce qui peut poser des problèmes de sécurité si le nom du fichier comprend des informations confidentielles.  En outre, le processus de génération utilisé par l'environnement de développement Visual C\+\+ invalidera la clé avec laquelle l'assembly est signé si vous avez utilisé des attributs CLR pour donner un nom fort à l'assembly, puis il exécutera un outil de post\-traitement tel que mt.exe sur cet assembly.  
  
 Si vous générez à la ligne de commande, utilisez les options de l'éditeur de liens pour signer votre assembly, puis exécutez un outil de post\-traitement \(comme mt.exe\), vous devrez ré\-signer l'assembly avec sn.exe.  Ou bien, vous pouvez générer et différer la signature de l'assembly et après avoir exécuté des outils de post\-traitement, complétez la signature.  
  
 Si vous utilisez les attributs de signature lors de la génération dans l'environnement de développement, vous pouvez signer correctement l'assembly en appelant explicitement sn.exe \([Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)\) dans un événement post\-build.  Pour plus d'informations, consultez [Spécification d'événements de build](../ide/specifying-build-events.md).  Les durées de génération peuvent être raccourcies si vous utilisez des attributs et un événement post\-build, par rapport à l'utilisation d'une option de l'éditeur de liens.  
  
 Les options de l'éditeur de liens suivantes prennent en charge la signature d'assembly :  
  
-   [\/DELAYSIGN \(Signer partiellement un assembly\)](../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYFILE \(Spécifier une clé ou une paire de clés pour signer un assembly\)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER \(Spécifier un conteneur de clé pour signer un assembly\)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 Pour plus d'informations sur les assemblys forts, consultez [Création et utilisation d'assemblys avec nom fort](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md).  
  
## Voir aussi  
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)