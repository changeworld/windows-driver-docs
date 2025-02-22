---
title: LanguageNeutralIdentifier
description: LanguageNeutralIdentifier
ms.date: 04/20/2017
---

# LanguageNeutralIdentifier

[!include[MBAE deprecation warning](../includes/mbae-deprecation-warning.md)]

The LanguageNeutralIdentifier element specifies a GUID, which identifies the service metadata package independent of its locale. The LanguageNeutralIdentifier element lets the same GUID be used to identify one or more localized versions of a service metadata package for the same service.

## Usage


``` syntax
<LanguageNeutralIdentifier>
  text
</LanguageNeutralIdentifier>
```

## Attributes


There are no attributes.

## Child elements


There are no child elements.

## Parent elements


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Element</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="relationships.md" data-raw-source="[Relationships](relationships.md)">Relationships</a></p></td>
<td><p>The <a href="relationships.md" data-raw-source="[Relationships](relationships.md)">Relationships</a> element specifies data that is used to track a device metadata package within the device metadata cache.</p></td>
</tr>
</tbody>
</table>

 

## XSD


``` syntax
<xs:element name="LanguageNeutralIdentifier" type="tns:GUIDType" minOccurs="0" />
```

## Remarks


The LanguageNeutralIdentifier element allows the same GUID to be used in one or more localized versions of a device metadata package for the same device.

For example, If you release a device for three locales (such as EN-US, JA-JP, and AR-SA), you can create separate metadata packages for the device for each locale. By using a common GUID for the LanguageNeutralIdentifier elements in these packages, you can easily search for the device's metadata package by browsing its PackageInfo XML document.

**Important**  
The LanguageNeutralIdentifier element is not used by any component of the operating system. It is reserved for use by the OEM, independent hardware vendor (IHV), and independent software vendor (ISV).\]

 

The LanguageNeutralIdentifier element is optional.

 

 





