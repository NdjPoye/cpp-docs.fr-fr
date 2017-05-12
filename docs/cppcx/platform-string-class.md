---
title: "Platform::String, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String"
ms.assetid: 72dd04a4-a694-40d3-b899-eaa0b503eab8
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::String, classe
Représente une collection séquentielle de caractères Unicode utilisée pour représenter du texte. Pour plus d'informations et d'exemples, consultez [Chaînes](../cppcx/strings-c-cx.md).  
  
## Syntaxe  
  
```cpp  
  
public ref class String sealed : Object,  
    IDisposable,  
    IEquatable,  
    IPrintable  
```  
  
## Itérateurs  
 Deux fonctions d'itérateur, qui ne sont pas membres de la classe String, peuvent être utilisées avec la fonction de modèle `std::for_each` pour énumérer les caractères d'un objet String.  
  
|Membre|Description|  
|------------|-----------------|  
|`const char16* begin(String^ s)`|Retourne un pointeur au début de l'objet String spécifié.|  
|`const char16* end(String^ s)`|Retourne un pointeur après la fin de l'objet String spécifié.|  
  
## Membres  
 La classe String hérite de la classe Object et des interfaces IDisposable, IEquatable et IPrintable.  
  
 La classe String a également les types de membres ci\-dessous.  
  
 **Constructeurs**  
  
|Membre|Description|  
|------------|-----------------|  
|[String::String, constructeur](../cppcx/string-string-constructor.md)|Initialise une nouvelle instance de la classe String.|  
  
 **Méthodes**  
  
 La classe String hérite des méthodes Equals\(\), Finalize\(\), GetHashCode\(\), GetType\(\), MemberwiseClose\(\) et ToString\(\) de la [Platform::Object, classe](../cppcx/platform-object-class.md). La classe String contient également les méthodes ci\-dessous.  
  
|Méthode|Description|  
|-------------|-----------------|  
|[String::Begin, méthode](../cppcx/string-begin-method.md)|Retourne un pointeur au début de la chaîne actuelle.|  
|[String::CompareOrdinal, méthode](../cppcx/string-compareordinal-method.md)|Compare deux objets `String` en évaluant les valeurs numériques des caractères correspondants dans les deux valeurs de chaîne représentées par les objets.|  
|[String::Concat, méthode](../cppcx/string-concat-method.md)|Concatène les valeurs de deux objets String.|  
|[String::Data, méthode](../cppcx/string-data-method.md)|Retourne un pointeur au début de la chaîne actuelle.|  
|[String::Dispose, méthode](../cppcx/string-dispose-method.md)|Libère des ressources.|  
|[String::End, méthode](../cppcx/string-end-method.md)|Retourne un pointeur après la fin de la chaîne actuelle.|  
|[String::Equals, méthode](../cppcx/string-equals-method.md)|Indique si l'objet spécifié est égal à l'objet actif.|  
|[String::GetHashCode, méthode](../cppcx/string-gethashcode-method.md)|Retourne le code de hachage de cette instance.|  
|[String::IsEmpty, méthode](../cppcx/string-isempty-method.md)|Indique si l'objet String actuel est vide.|  
|[String::IsFastPass, méthode](../cppcx/string-isfastpass-method.md)|Indique si l'objet String actuel participe à une opération de *passage rapide*. Dans une opération de passage rapide, le comptage des références est interrompu.|  
|[String::Length, méthode](../cppcx/string-length-method.md)|Récupère la longueur de l'objet String en cours.|  
|[String::ToString, méthode](../cppcx/string-tostring-method-c-cx.md)|Retourne un objet String dont la valeur est identique à celle de la chaîne en cours.|  
  
 **Propriétés**  
  
 La classe String a les propriétés ci\-dessous.  
  
|Membre|Description|  
|------------|-----------------|  
|[String::operator\=\=, opérateur](../cppcx/string-operator-equality-operator-c-cx.md)|Indique si deux objets String spécifiés ont la même valeur.|  
|[Opérateur opérateur\+](../cppcx/string-operator-decrementoperator.md)|Concatène deux objets String en un nouvel objet String.|  
|[String::operator\>, opérateur](../cppcx/string-operator-greater-than-operator-c-cx.md)|Indique si la valeur d'un objet String est supérieure à la valeur d'un deuxième objet String.|  
|[String::operator\>\=, opérateur](../cppcx/string-operator-greater-than-or-equals-c-cx.md)|Indique si la valeur d'un objet String est supérieure ou égale à la valeur d'un deuxième objet String.|  
|[String::operator\!\=, opérateur](../cppcx/string-operator-inequality-operator-c-cx.md)|Indique si deux objets String spécifiés ont des valeurs différentes.|  
|[String::operator\<, opérateur](../cppcx/string-operator-less-than-operator-c-cx.md)|Indique si la valeur d'un objet String est inférieure à la valeur d'un deuxième objet String.|  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **En\-tête** vccorlib.h \(inclus par défaut\)  
  
## Voir aussi  
 [Espace de noms de plateforme](../cppcx/platform-namespace-c-cx.md)