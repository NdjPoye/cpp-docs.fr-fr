---
title: "S&#233;rialisation&#160;: d&#233;finir une classe s&#233;rialisable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes (C++), dérivés"
  - "CObject (classe), dériver des classes sérialisables"
  - "constructeurs [C++], définir sans arguments"
  - "DECLARE_SERIAL (macro)"
  - "constructeur par défaut"
  - "valeurs par défaut (C++), constructeur"
  - "IMPLEMENT_SERIAL (macro)"
  - "constructeur par défaut (absence)"
  - "constructeur sans arguments"
  - "classe sérialisable"
  - "sérialisation (C++), classes sérialisables"
  - "Serialize (méthode), substituer"
  - "VERSIONABLE_SCHEMA (macro)"
ms.assetid: 59a14d32-1cc8-4275-9829-99639beee27c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# S&#233;rialisation&#160;: d&#233;finir une classe s&#233;rialisable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cinq étapes principales sont requises pour rendre une classe sérialisable.  Elles sont répertoriées ci\-dessous et expliquées dans les sections suivantes :  
  
1.  [Dérivation de la classe de CObject](#_core_deriving_your_class_from_cobject) \(ou une certaine classe dérivée de `CObject`\).  
  
2.  [Remplacer la fonction membre Serialize](#_core_overriding_the_serialize_member_function).  
  
3.  [À l'aide de la macro de DECLARE\_SERIAL](#_core_using_the_declare_serial_macro) dans la déclaration de classe.  
  
4.  [Définition d'un constructeur qui n'accepte aucun argument](#_core_defining_a_constructor_with_no_arguments).  
  
5.  [À l'aide de la macro d'IMPLEMENT\_SERIAL dans le fichier d'implémentation](#_core_using_the_implement_serial_macro_in_the_implementation_file) pour votre classe.  
  
 Si vous appelez `Serialize` directement plutôt que dans \>\> et \<\< les opérateurs de [CArchive](../mfc/reference/carchive-class.md), les trois dernières étapes ne sont pas nécessaires à la sérialisation.  
  
##  <a name="_core_deriving_your_class_from_cobject"></a> Dérivation de votre classe de CObject  
 Protocole et les fonctionnalités de base de sérialisation sont définis dans la classe `CObject`.  En faisant dériver votre classe de `CObject` \(ou une classe dérivée de `CObject`\), comme indiqué dans la déclaration suivante de la classe `CPerson`, vous accédez au protocole de sérialisation et la fonctionnalité de `CObject`.  
  
##  <a name="_core_overriding_the_serialize_member_function"></a> Remplacement de la fonction membre Serialize.  
 La fonction membre `Serialize`, définie dans la classe `CObject`, est chargée de sérialisation réellement les données nécessaires pour capturer l'état actuel d'un objet.  La fonction `Serialize` a un argument `CArchive` qu'elle utilise à lire et écrire les données de l'objet.  L'objet [CArchive](../mfc/reference/carchive-class.md) fournit une fonction membre, `IsStoring`, qui indique si `Serialize` journaux \(écriture de données\) ou chargement de données \(lecture\).  Utilisation des résultats de `IsStoring` comme guide, vous insérez les données de l'objet dans l'objet `CArchive` avec les données d'insertion d'opérateur \(**\<\<**\) ou extract avec l'opérateur d'extraction \(**\>\>**\).  
  
 Supposons une classe dérivée de `CObject` et possède deux variables membres, des types `CString` et **WORD**.  Le fragment de déclaration de classe présente les variables membres et la déclaration de la fonction membre substituée de `Serialize`:  
  
 [!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/CPP/serialization-making-a-serializable-class_1.h)]  
  
#### Ecraser la fonction membre Serialize.  
  
1.  Appelez votre version de la classe de base de `Serialize` pour vérifier que la partie héritée de l'objet est sérialisée.  
  
2.  Insérer ou extraire des variables membres spécifiques à votre classe.  
  
     L'insertion et les opérateurs d'extraction interagissent avec la classe d'archive à lire et écrire les données.  L'exemple suivant montre comment implémenter `Serialize` pour la classe `CPerson` déclarée ci\-dessus :  
  
     [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/CPP/serialization-making-a-serializable-class_2.cpp)]  
  
 Vous pouvez également utiliser les fonctions membres [CArchive::Read](../Topic/CArchive::Read.md) et [CArchive::Write](../Topic/CArchive::Write.md) en lecture et en écriture grandes quantités de données non typées.  
  
##  <a name="_core_using_the_declare_serial_macro"></a> À l'aide de la macro de DECLARE\_SERIAL  
 La macro `DECLARE_SERIAL` est requise dans la déclaration des classes qui prennent en charge la sérialisation, comme indiqué ici :  
  
 [!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/CPP/serialization-making-a-serializable-class_3.h)]  
  
##  <a name="_core_defining_a_constructor_with_no_arguments"></a> Définir un constructeur sans arguments  
 MFC requiert un constructeur par défaut lorsqu'il recrée les objets tels qu'ils sont désérialisés \(chargé du disque\).  Le processus de désérialisation complétera toutes les variables membres avec les valeurs requises pour recréer l'objet.  
  
 Ce constructeur peut être déclaré public, protégé, ou privé.  Si vous le rendez protégé ou privé, vous aide à vous assurer qu'il sera utilisé uniquement par les fonctions de sérialisation.  Le constructeur doit mettre l'objet dans un état qui l'autorise à supprimer si nécessaire.  
  
> [!NOTE]
>  Si vous oubliez de définir un constructeur sans arguments dans une classe qui utilise les macros `DECLARE_SERIAL` et `IMPLEMENT_SERIAL`, vous obtiendrez un message « aucun constructeur par défaut » l'avertissement du compilateur disponible dans la ligne où la macro `IMPLEMENT_SERIAL` est utilisée.  
  
##  <a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a> À l'aide de la macro d'IMPLEMENT\_SERIAL dans le fichier d'implémentation  
 La macro `IMPLEMENT_SERIAL` permet de définir diverses fonctions nécessaires lorsque vous dérivez une classe `CObject`sérialisable.  Vous utilisez la macro du fichier d'implémentation \(.CPP\) pour la classe.  Les deux premiers arguments à la macro est le nom de la classe et le nom de la classe de base immédiate.  
  
 Le troisième argument de la macro est un nombre de schéma.  Le numéro schéma est essentiellement un numéro de version des objets de la classe.  Utilisez un entier supérieur ou égal à 0 et du numéro de schéma. \(Ne confondez pas le nombre de schéma avec la terminologie de base de données.\)  
  
 Les contrôles de code de sérialisation de MFC numéro génération de schéma lors de la lecture des objets en mémoire.  Si le nombre schéma de l'objet sur le disque ne correspond pas au nombre le schéma de la classe en mémoire, la bibliothèque lève `CArchiveException`, empêchant votre programme de lire une version incorrecte de l'objet.  
  
 Si vous souhaitez que votre fonction membre `Serialize` puisse lire plusieurs versions \- c'est\-à\-dire, fichiers écrits avec différentes versions de l'application — vous pouvez utiliser la valeur **VERSIONABLE\_SCHEMA** comme argument de la macro `IMPLEMENT_SERIAL`.  Pour les informations d'utilisation et un exemple, consultez la fonction membre `GetObjectSchema` de la classe `CArchive`.  
  
 L'exemple suivant indique comment utiliser `IMPLEMENT_SERIAL` pour une classe, `CPerson`, qui dérive de `CObject`:  
  
 [!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/CPP/serialization-making-a-serializable-class_4.cpp)]  
  
 Une fois que vous avez une classe sérialisable, vous pouvez sérialiser des objets de la classe, comme décrit dans l'article [Sérialisation : Sérialiser un objet](../mfc/serialization-serializing-an-object.md).  
  
## Voir aussi  
 [Sérialisation](../mfc/serialization-in-mfc.md)