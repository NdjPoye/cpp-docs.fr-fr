---
title: "Meilleures pratiques pour la s&#233;curit&#233; dans le Kit de d&#233;veloppement logiciel (SDK) Visual Studio | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "sécurité [Kit de développement logiciel (SDK) Visual Studio]"
  - "Contrôle de compte d’utilisateur [Kit de développement logiciel (SDK) Visual Studio]"
  - "Kit de développement logiciel (SDK) Visual Studio, sécurité"
  - "UAC (contrôle de compte d’utilisateur) [Kit de développement logiciel (SDK) Visual Studio]"
  - "meilleures pratiques pour la sécurité, Kit de développement logiciel (SDK) Visual Studio"
  - "Windows Vista, contrôle de compte d’utilisateur [Kit de développement logiciel (SDK) Visual Studio]"
ms.assetid: 56c8a113-0c53-4969-a009-a2ab58d855c3
caps.latest.revision: 30
caps.handback.revision: 30
manager: "douge"
---
# Meilleures pratiques pour la s&#233;curit&#233; dans le Kit de d&#233;veloppement logiciel (SDK) Visual Studio
Vous devez comprendre la sécurité des extensions VSPackage pour pouvoir créer les meilleurs produits possibles.  
  
 Un produit sécurisé permet de protéger les éléments suivants :  
  
-   Confidentialité, intégrité et disponibilité des informations d’un client  
  
-   Intégrité et disponibilité des ressources de traitement sous le contrôle du propriétaire ou de l’administrateur du système  
  
## Faille de sécurité  
 Une faille de sécurité est une faiblesse dans un produit qui le rend incapable d’empêcher les activités malveillantes d’un intrus, même quand le produit est utilisé correctement. Voici quelques exemples :  
  
-   Obtention d’autorisations sur un ordinateur supérieures à celles de l’utilisateur  
  
-   Prise de contrôle du fonctionnement de l’ordinateur d’un utilisateur  
  
-   Compromission des données sur l’ordinateur d’un utilisateur  
  
> [!IMPORTANT]
>  Ne partez jamais du principe que votre application sera exécutée uniquement dans des environnements spécifiques. Votre application peut être utilisée avec des paramètres que vous n’aviez pas prévus, en particulier quand elle gagne en popularité. Supposez plutôt que le code sera exécuté dans des environnements hostiles, donc concevez, rédigez et testez celui\-ci en conséquence.  
  
 Les produits et systèmes conçus et créés en donnant la priorité à la sécurité sont plus robustes que ceux développés en considérant la sécurité comme accessoire. Les produits sécurisés sont également plus à l’abri des critiques des médias, plus attrayants pour les utilisateurs et moins coûteux à prendre en charge et à mettre à niveau.  
  
## API dangereuses  
 Les appels à certaines fonctions peuvent produire des failles de sécurité indésirables si elles sont utilisées de manière incorrecte, mais l’interdiction de leur utilisation n’aboutit pas nécessairement à un code sécurisé. Néanmoins, certains projets logiciels ont obtenu des améliorations mesurables en matière de sécurité en interdisant des fonctions difficiles à utiliser en toute sécurité, comme l’une des nombreuses pratiques de développement sécurisé. Pour plus d’informations, consultez l’annexe A du livre Microsoft Press « Writing Secure Code » de Michael Howard et David LeBlanc.  
  
 La plupart des problèmes de sécurité résulte de l’approbation des entrées sans les avoir vérifiées de manière adéquate. Veillez à effectuer le suivi des données qui sont ajoutées à votre code et renseignez\-vous sur les implications des différentes opérations sur ces données. Vous pouvez écrire du code sécurisé en utilisant la plupart des fonctions si les entrées de données sont bien formées et que leur fiabilité a été vérifiée.  
  
## Problèmes liés au contrôle de compte d’utilisateur  
 La fonctionnalité de contrôle de compte d’utilisateur a des implications en matière de sécurité que vous devez connaître. Elle réduit l’exposition du système d’exploitation et des applications à des attaques malveillantes.  
  
1.  Pour plus d’informations sur le contrôle de compte d’utilisateur sur [!INCLUDE[win7](../build/includes/win7_md.md)], consultez [Qu’est\-ce que le contrôle de compte d’utilisateur ?](http://go.microsoft.com/fwlink/?linkid=159927).  
  
2.  Pour plus d’informations sur le contrôle de compte d’utilisateur sur [!INCLUDE[win8](../build/includes/win8_md.md)], consultez [Quels sont les paramètres du contrôle de compte d’utilisateur ?](http://windows.microsoft.com/windows-8/what-are-uac-settings).  
  
 Avant l’arrivée du contrôle de compte d’utilisateur, les développeurs exécutaient généralement [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] avec des autorisations d’administrateur même quand elles n’étaient pas obligatoires. Vous devez effectuer le développement et le test de votre extension en tant qu’utilisateur normal, afin de vérifier que vous n’avez pas besoin de droits élevés.  
  
 Notez que le contrôle de compte d’utilisateur affecte également le déploiement. Les packages d’installation doivent être correctement créés pour prendre en charge le contrôle de compte d’utilisateur. Un package créé de manière incorrecte provoque généralement des erreurs de type « accès refusé », car le programme d’installation tente d’utiliser des droits d’utilisateur normal pour effectuer une tâche qui requiert des droits élevés.  
  
## Voir aussi  
 [Meilleures pratiques pour la sécurité dans les packages VS](../Topic/Best%20Practices%20for%20Security%20in%20VSPackages.md)   
 [Ressources de création des applications sécurisées](http://msdn.microsoft.com/fr-fr/0ebf5f69-76f2-498a-a2df-83cf3443e132)   
 [Concepts fondamentaux sur la sécurité](../Topic/Key%20Security%20Concepts.md)