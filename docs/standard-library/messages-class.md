---
title: messages, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmes/std::messages
- xlocmes/std::messages::char_type
- xlocmes/std::messages::string_type
- xlocmes/std::messages::close
- xlocmes/std::messages::do_close
- xlocmes/std::messages::do_get
- xlocmes/std::messages::do_open
- xlocmes/std::messages::get
- xlocmes/std::messages::open
dev_langs:
- C++
helpviewer_keywords:
- std::messages [C++]
- std::messages [C++], char_type
- std::messages [C++], string_type
- std::messages [C++], close
- std::messages [C++], do_close
- std::messages [C++], do_get
- std::messages [C++], do_open
- std::messages [C++], get
- std::messages [C++], open
ms.assetid: c4c71f40-4f24-48ab-9f7c-daccd8d5bd83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ffc59d3425f403fb1dca43f70876cfbfb5d3dd9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="messages-class"></a>messages, classe

Cette classe de modèle décrit un objet pouvant servir de facette de paramètres régionaux pour récupérer des messages localisés à partir d'un catalogue de messages internationalisés pour des paramètres régionaux donnés.

Actuellement, lorsque la classe de messages est implémentée, il n'y a aucun message.

## <a name="syntax"></a>Syntaxe

```cpp
template <class CharType>
class messages : public messages_base;
```

### <a name="parameters"></a>Paramètres

`CharType` Le type utilisé dans un programme pour encoder des caractères dans des paramètres régionaux.

## <a name="remarks"></a>Notes

Comme avec n'importe quelle facette de paramètres régionaux, l'ID d'objet statique possède une valeur stockée initiale de zéro. La première tentative d’accès à sa valeur stockée entraîne le stockage d’une valeur positive unique dans **id.**

Cette facette ouvre un catalogue de messages définis dans la classe de base messages_base, récupère les informations requises et ferme le catalogue.

### <a name="constructors"></a>Constructeurs

|Constructeur|Description|
|-|-|
|[messages](#messages)|Fonction constructeur de facette de message.|

### <a name="typedefs"></a>Typedef

|Nom de type|Description|
|-|-|
|[char_type](#char_type)|Type de caractère utilisé pour afficher les messages.|
|[string_type](#string_type)|Type qui décrit une chaîne de type `basic_string` qui contient des caractères de type `CharType`.|

### <a name="member-functions"></a>Fonctions membres

|Fonction membre|Description|
|-|-|
|[close](#close)|Ferme le catalogue de messages.|
|[do_close](#do_close)|Fonction virtuelle appelée pour fermer le catalogue de messages.|
|[do_get](#do_get)|Fonction virtuelle appelée pour récupérer le catalogue de messages.|
|[do_open](#do_open)|Fonction virtuelle appelée pour ouvrir le catalogue de messages.|
|[get](#get)|Récupère le catalogue de messages.|
|[open](#open)|Ouvre le catalogue de messages.|

## <a name="requirements"></a>Spécifications

**En-tête :** \<locale>

**Espace de noms :** std

## <a name="char_type"></a>  messages::char_type

Type de caractère utilisé pour afficher les messages.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Notes

Le type est un synonyme du paramètre de modèle **CharType**.

## <a name="close"></a>  messages::close

Ferme le catalogue de messages.

```cpp
void close(catalog _Catval) const;
```

### <a name="parameters"></a>Paramètres

`_Catval` Le catalogue doit être fermé.

### <a name="remarks"></a>Notes

La fonction membre appelle [do_close](#do_close)(_ *Catval*).

## <a name="do_close"></a>  messages::do_close

Fonction virtuelle appelée pour fermer le catalogue de messages.

```cpp
virtual void do_close(catalog _Catval) const;
```

### <a name="parameters"></a>Paramètres

`_Catval` Le catalogue doit être fermé.

### <a name="remarks"></a>Notes

La fonction membre ferme le catalogue de messages `_Catval`, qui doit avoir été ouvert par un appel précédent à [do_open](#do_open).

*_Catval* doit être obtenu à partir d’un catalogue précédemment ouvert qui n’est pas fermé.

### <a name="example"></a>Exemple

Consultez l’exemple relatif à [close](#close), qui appelle `do_close`.

## <a name="do_get"></a>  messages::do_get

Fonction virtuelle appelée pour récupérer le catalogue de messages.

```cpp
virtual string_type do_get(
    catalog _Catval,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```

### <a name="parameters"></a>Paramètres

`_Catval` La valeur d’identification en spécifiant le catalogue de messages à rechercher.

`_Set` La première identifié utilisé pour rechercher un message dans un catalogue de messages.

`_Message` La seconde identifié utilisé pour rechercher un message dans un catalogue de messages.

`_Dfault` La chaîne à retourner en cas d’échec.

### <a name="return-value"></a>Valeur de retour

Retourne une copie de `_Dfault` en cas d’échec. Sinon, retourne une copie de la séquence de message spécifiée.

### <a name="remarks"></a>Notes

La fonction membre protégée tente d’obtenir une séquence de message à partir du catalogue de messages `_Catval`. Elle peut utiliser `_Set`, `_Message` et `_Dfault` lors de cette tentative.

### <a name="example"></a>Exemple

Consultez l’exemple relatif à [get](#get), qui appelle `do_get`.

## <a name="do_open"></a>  messages::do_open

Fonction virtuelle appelée pour ouvrir le catalogue de messages.

```cpp
virtual catalog do_open(
    const string& _Catname,
    const locale& _Loc) const;
```

### <a name="parameters"></a>Paramètres

`_Catname` Le nom du catalogue à rechercher.

`_Loc` Les paramètres régionaux en cours de recherche dans le catalogue.

### <a name="return-value"></a>Valeur de retour

Retourne une valeur inférieure à zéro en cas d’échec. Dans le cas contraire, la valeur retournée peut être utilisée comme premier argument lors d’un appel ultérieur à [get](#get).

### <a name="remarks"></a>Notes

La fonction membre protégée tente d’ouvrir un catalogue de messages dont le nom est `_Catname`. Elle peut utiliser les paramètres régionaux `_Loc` lors de cette tentative.

La valeur de retour doit être utilisée comme argument lors d’un appel ultérieur à [close](#close).

### <a name="example"></a>Exemple

Consultez l’exemple relatif à [open](#open), qui appelle `do_open`.

## <a name="get"></a>  messages::get

Récupère le catalogue de messages.

```cpp
string_type get(
    catalog _CatVal,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```

### <a name="parameters"></a>Paramètres

`_Catval` La valeur d’identification en spécifiant le catalogue de messages à rechercher.

`_Set` La première identifié utilisé pour rechercher un message dans un catalogue de messages.

`_Message` La seconde identifié utilisé pour rechercher un message dans un catalogue de messages.

`_Dfault` La chaîne à retourner en cas d’échec.

### <a name="return-value"></a>Valeur de retour

Retourne une copie de `_Dfault` en cas d’échec. Sinon, retourne une copie de la séquence de message spécifiée.

### <a name="remarks"></a>Notes

La fonction membre retourne [do_get](#do_get)( `_Catval`, `_Set`, `_Message`, `_Dfault`).

## <a name="messages"></a>  messages::messages

Fonction constructeur de facette de message.

```cpp
explicit messages(
    size_t _Refs = 0);

protected: messages(
    const char* _Locname,
    size_t _Refs = 0);
```

### <a name="parameters"></a>Paramètres

`_Refs` Valeur entière qui sert à spécifier le type de gestion de la mémoire pour l’objet.

`_Locname` Le nom des paramètres régionaux.

### <a name="remarks"></a>Notes

Les valeurs possibles pour le paramètre `_Refs` et leur signification sont les suivantes :

- 0 : la durée de vie de l’objet est gérée par les paramètres régionaux qui le contiennent.

- 1 : la durée de vie de l’objet doit être gérée manuellement.

- \> 1 : ces valeurs ne sont pas définis.

Aucun exemple direct n’est possible, car le destructeur est protégé.

Le constructeur initialise son objet de base avec **locale::**[facet](../standard-library/locale-class.md#facet_class)( `_Refs`).

## <a name="open"></a>  messages::open

Ouvre le catalogue de messages.

```cpp
catalog open(
    const string& _Catname,
    const locale& _Loc) const;
```

### <a name="parameters"></a>Paramètres

`_Catname` Le nom du catalogue à rechercher.

`_Loc` Les paramètres régionaux en cours de recherche dans le catalogue.

### <a name="return-value"></a>Valeur de retour

Retourne une valeur inférieure à zéro en cas d’échec. Dans le cas contraire, la valeur retournée peut être utilisée comme premier argument lors d’un appel ultérieur à [get](#get).

### <a name="remarks"></a>Notes

La fonction membre retourne [do_open](#do_open)( `_Catname`, `_Loc`).

## <a name="string_type"></a>  messages::string_type

Type qui décrit une chaîne de type `basic_string` contenant des caractères de type **CharType**.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Notes

Le type décrit une spécialisation de la classe de modèle [basic_string](../standard-library/basic-string-class.md) dont les objets peuvent stocker des copies des séquences de messages.

## <a name="see-also"></a>Voir aussi

[\<locale>](../standard-library/locale.md)<br/>
[messages_base, classe](../standard-library/messages-base-class.md)<br/>
[Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
