---
title: "R&#233;solution des probl&#232;mes li&#233;s aux exceptions de s&#233;curit&#233; d’acc&#232;s du code | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "CodeAccessPermission, classe"
  - "CodeAccessSecurityException, classe"
  - "sécurité d’accès du code, résolution des problèmes"
  - "sécurité (débogueur], résolution des problèmes de sécurité d’accès du code"
  - "résolution des problèmes de sécurité d’accès du code"
ms.assetid: ca368d3b-f6d0-4c89-af59-d94f343fca35
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# R&#233;solution des probl&#232;mes li&#233;s aux exceptions de s&#233;curit&#233; d’acc&#232;s du code
Les autorisations contrôlent ce que votre code est autorisé à faire et ne pas faire. Au moment de l’exécution d’une application, celle\-ci reçoit un jeu d’autorisations par le runtime. Si elle dispose d’autorisations suffisantes, elle s’exécute correctement ; sinon, une exception de sécurité se produit.  
  
 Les autorisations accordées à votre code sont déterminées par l’emplacement depuis lequel l’application a été lancée \(par exemple, Internet, un réseau intranet ou l’ordinateur local\) et les paramètres de sécurité de l’ordinateur sur lequel l’application s’exécute. Comme ces paramètres peuvent différer d’un ordinateur à un autre, vous ne pouvez pas toujours anticiper si oui ou non le code recevra les autorisations suffisantes.  
  
 La demande d’autorisation garantit que votre code s’exécutera si la stratégie de sécurité de l’ordinateur local le permet. Si vous ne demandez pas les autorisations nécessaires, vous courez le risque de ne pas obtenir l’exécution de votre code. Pour plus d’informations sur les autorisations d’accès du code, consultez [Autorisations d’accès du code](http://msdn.microsoft.com/fr-fr/e5ae402f-6dda-4732-bbe8-77296630f675) ou [NIB : demande d’autorisations](http://msdn.microsoft.com/fr-fr/0447c49d-8cba-45e4-862c-ff0b59bebdc2). Pour plus d’informations sur les blocs `Try...Catch`, consultez [Try...Catch...Finally Statement](../Topic/Try...Catch...Finally%20Statement%20\(Visual%20Basic\).md).  
  
 Les applications [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] peuvent demander des autorisations supplémentaires, si nécessaire, à l’aide de la page Sécurité du Concepteur d’applications. Pour plus d’informations, consultez [Comment : définir des autorisations personnalisées pour une application ClickOnce](../Topic/How%20to:%20Set%20Custom%20Permissions%20for%20a%20ClickOnce%20Application.md).  
  
 Voici quelques causes possibles aux exceptions de sécurité d’accès du code :  
  
-   **Presse\-papiers.** Le collage à partir du Presse\-papiers par programme est une fonctionnalité restreinte du code managé, parce que le Presse\-papiers peut contenir des informations sensibles.  
  
-   **Accès au Registre ou au système de fichiers.** Accès restreint au système de fichiers local. Si vous accédez à un fichier ou à une ressource déployés avec votre assembly, utilisez le code `Assembly.GetExecutingAssembly.Location` pour obtenir le chemin d’accès à votre assembly.  
  
-   **Accès au réseau.** Assurez\-vous que votre assembly utilise le même protocole que celui avec lequel il a été chargé. En général, seule l’URL source de l’assembly est autorisée à communiquer par réseau.  
  
-   **Impression.** Les logiciels exécutés dans la zone Internet ne peuvent imprimer qu’en passant par une boîte de dialogue commune. L’impression est limitée à l’imprimante par défaut sauf si le logiciel donne accès à une boîte de dialogue commune dans laquelle l’utilisateur peut sélectionner une imprimante.  
  
-   **Sérialisation.** La possibilité de régénérer un objet à partir de données arbitraires est limitée au code exécuté avec un niveau de confiance total. Dans le cas d’une sérialisation XML, le type `XmlSerializer` doit être techniquement utilisable par du code d’un niveau de confiance partiel. Pour plus d’informations sur le type `XmlSerializer`, consultez [XmlSerializer, classe](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx).  
  
-   **Réflexion.** Un grand nombre des fonctionnalités d’exécution liées à la réflexion ont un usage limité en raison du niveau de confiance partiel du code.  
  
## Test de code pour déterminer s’il lève une exception de sécurité d’accès du code  
 Si un bloc de code risque de lever une `CodeAccessSecurityException`, utilisez un bloc `Try...Catch` pour autoriser l’exécution du code si c’est possible et remédier à l’erreur sinon.  
  
 Il peut être utile d’ajuster le comportement de votre application en fonction des autorisations que le système hôte lui a accordées. Par exemple, il peut s’avérer utile de désactiver une commande d’impression dans un menu si l’application n’a pas d’autorisations d’impression.  
  
 Pour le tester, vous pouvez créer une instance d’une classe dérivée de `CodeAccessPermission`, telle que `FileIOPermission`. Ensuite, vous pouvez exécuter la méthode `Demand` sur l’autorisation dans un bloc `Try...Catch`. Si l’exception est levée, votre assembly n’a pas l’autorisation.  
  
 L’exemple suivant teste si l’assembly a l’autorisation `EventLogPermission` en exécutant ou en créant une `EventLogPermission` et en exécutant sa méthode `Demand` dans un bloc `Try...Catch` pour déterminer si oui ou non la `Demand` aboutit.  
  
```  
Try Dim MyPermission As New EventLogPermission MyPermission.Demand() MsgBox(MyPermission.ToString()) Catch ex As Exception MsgBox("Assembly lacks EventLogPermission.") End Try  
```  
  
## Voir aussi  
 [Autorisations d’accès du code](http://msdn.microsoft.com/fr-fr/e5ae402f-6dda-4732-bbe8-77296630f675)   
 [NIB : demande d’autorisations](http://msdn.microsoft.com/fr-fr/0447c49d-8cba-45e4-862c-ff0b59bebdc2)   
 [Notions fondamentales de la sécurité d'accès du code](../Topic/Code%20Access%20Security%20Basics.md)