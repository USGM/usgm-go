# Reference
## mails
<details><summary><code>client.Mails.List() -> *usgm.MailPageDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List your mail items with filtering, search, sorting and cursor pagination
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.MailsListRequest{}
client.Mails.List(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*int` — Page size, capped at 100.
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — Opaque page cursor — the `next_cursor` of the previous response. Omit for the first page.
    
</dd>
</dl>

<dl>
<dd>

**status:** `*usgm.MailsListRequestStatusItem` 
    
</dd>
</dl>

<dl>
<dd>

**mailType:** `*usgm.MailsListRequestMailTypeItem` 
    
</dd>
</dl>

<dl>
<dd>

**folderID:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**search:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**scanStatus:** `*usgm.MailsListRequestScanStatusItem` — Filter by the item’s scan state; `none` selects items with no scan.
    
</dd>
</dl>

<dl>
<dd>

**sort:** `*usgm.MailsListRequestSort` 
    
</dd>
</dl>

<dl>
<dd>

**arrived:** `*usgm.MailsListRequestArrived` 
    
</dd>
</dl>

<dl>
<dd>

**isRead:** `*usgm.MailsListRequestIsRead` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Mails.Get(ID) -> *usgm.MailDetailDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve full detail for one mail item, including dimensions, weight and folder
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.MailsGetRequest{
        ID: "id",
    }
client.Mails.Get(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Mails.Update(ID, request) -> *usgm.MailDetailDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Mark the item read/unread and/or move it into a folder
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.UpdateMailDto{
        ID: "id",
    }
client.Mails.Update(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**isRead:** `*bool` 
    
</dd>
</dl>

<dl>
<dd>

**folderID:** `*string` — Move the item to this folder. Pass null to remove it from its folder.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Mails.Archive(ID) -> *usgm.MailDetailDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Move the item out of your active inbox into the archive
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.MailsArchiveRequest{
        ID: "id",
    }
client.Mails.Archive(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Mails.Unarchive(ID) -> *usgm.MailDetailDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Restore an archived item back to its previous inbox status
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.MailsUnarchiveRequest{
        ID: "id",
    }
client.Mails.Unarchive(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Mails.Discard(ID) -> *usgm.MailDetailDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Request the mailroom to discard the physical item; destructive, reverse with undiscard within 7 days after the discard request. After 7 days the mail item will be permanently and securely shredded and discarded
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.MailsDiscardRequest{
        ID: "id",
    }
client.Mails.Discard(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Mails.Undiscard(ID) -> *usgm.MailDetailDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Cancel a pending discard request and keep the item
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.MailsUndiscardRequest{
        ID: "id",
    }
client.Mails.Undiscard(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## scans
<details><summary><code>client.Scans.List() -> *usgm.ScanPageDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List your scan and open-and-scan requests, with filtering, search and pagination
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.ScansListRequest{}
client.Scans.List(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*int` — Page size, capped at 100.
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — Opaque page cursor — the `next_cursor` of the previous response. Omit for the first page.
    
</dd>
</dl>

<dl>
<dd>

**status:** `*usgm.ScansListRequestStatusItem` 
    
</dd>
</dl>

<dl>
<dd>

**type_:** `*usgm.ScansListRequestTypeItem` — `scan` (scan the item) or `open` (open it and scan the contents).
    
</dd>
</dl>

<dl>
<dd>

**mailID:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**search:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**sort:** `*usgm.ScansListRequestSort` 
    
</dd>
</dl>

<dl>
<dd>

**scanned:** `*usgm.ScansListRequestScanned` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Scans.Create(request) -> *usgm.ScanDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Request a scan or open-and-scan of a mail item; this is a billable action
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.CreateScanDto{
        MailID: "mail_id",
        Type: usgm.CreateScanDtoTypeScan,
    }
client.Scans.Create(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**mailID:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**type_:** `*usgm.CreateScanDtoType` — `scan` scans the item as-is; `open` opens it and scans the contents.
    
</dd>
</dl>

<dl>
<dd>

**instruction:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**isExpedited:** `*bool` — Expedited handling — may incur an extra charge.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Scans.Get(ID) -> *usgm.ScanDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve one scan request by its id, including status and AI label
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.ScansGetRequest{
        ID: "id",
    }
client.Scans.Get(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Scans.Delete(ID) -> *usgm.ScanDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Permanently delete a scan and remove its stored file; this cannot be undone
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.ScansDeleteRequest{
        ID: "id",
    }
client.Scans.Delete(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Scans.File(ID) -> *usgm.ScanFileDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return a short-lived signed URL to download the scanned document; fetch it promptly
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.ScansFileRequest{
        ID: "id",
    }
client.Scans.File(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Scans.Summary(ID) -> *usgm.ScanSummaryDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return the AI-generated label and bullet summary of the scanned document
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.ScansSummaryRequest{
        ID: "id",
    }
client.Scans.Summary(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Scans.Cancel(ID) -> *usgm.ScanDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Cancel a scan request you no longer need. Valid only for scan requests in in_process status
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.ScansCancelRequest{
        ID: "id",
    }
client.Scans.Cancel(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## shipments
<details><summary><code>client.Shipments.List() -> *usgm.ShipmentPageDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Read-only list of your shipment requests, filterable by type and status
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.ShipmentsListRequest{}
client.Shipments.List(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*int` — Page size, capped at 100.
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — Opaque page cursor — the `next_cursor` of the previous response. Omit for the first page.
    
</dd>
</dl>

<dl>
<dd>

**type_:** `*usgm.ShipmentsListRequestTypeItem` 
    
</dd>
</dl>

<dl>
<dd>

**status:** `*usgm.ShipmentsListRequestStatusItem` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Shipments.Get(ID) -> *usgm.ShipmentDetailDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Read-only details of one shipment, including its packed mail items
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.ShipmentsGetRequest{
        ID: "id",
    }
client.Shipments.Get(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## folders
<details><summary><code>client.Folders.List() -> *usgm.FolderListDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

All your mail folders, returned unpaginated
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Folders.List(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Folders.Create(request) -> *usgm.FolderDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new mail folder with a name and optional color
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.CreateFolderDto{
        Name: "name",
    }
client.Folders.Create(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**color:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Folders.Get(ID) -> *usgm.FolderDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve one mail folder by its id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.FoldersGetRequest{
        ID: "id",
    }
client.Folders.Get(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Folders.Delete(ID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a folder and unfile its mail, which is not deleted
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.FoldersDeleteRequest{
        ID: "id",
    }
client.Folders.Delete(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Folders.Update(ID, request) -> *usgm.FolderDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Rename a folder or change its color
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.UpdateFolderDto{
        ID: "id",
    }
client.Folders.Update(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**name:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**color:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## addresses
<details><summary><code>client.Addresses.List() -> *usgm.AddressPageDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List your shipping and deposit addresses, optionally filtered by type
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.AddressesListRequest{}
client.Addresses.List(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*int` — Page size, capped at 100.
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — Opaque page cursor — the `next_cursor` of the previous response. Omit for the first page.
    
</dd>
</dl>

<dl>
<dd>

**type_:** `*usgm.AddressesListRequestType` — `shipping` = a shipment destination; `deposit` = where check deposits are sent.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Addresses.Create(request) -> *usgm.AddressDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Add a new shipping or check-deposit address to your account
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.CreateAddressDto{
        Type: usgm.CreateAddressDtoTypeShipping,
        Name: "name",
        Line1: "line1",
        City: "city",
        State: "state",
        PostalCode: "postal_code",
        Country: "country",
        PhoneNumber: "phone_number",
    }
client.Addresses.Create(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**type_:** `*usgm.CreateAddressDtoType` — `shipping` = a shipment destination; `deposit` = where check deposits are sent.
    
</dd>
</dl>

<dl>
<dd>

**name:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**line1:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**line2:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**line3:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**city:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**state:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**postalCode:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**country:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**phoneNumber:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**taxID:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Addresses.Getdefault() -> *usgm.AddressDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get your default address for a given type, shipping or deposit
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.AddressesGetDefaultRequest{
        Type: usgm.AddressesGetDefaultRequestTypeShipping,
    }
client.Addresses.Getdefault(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**type_:** `*usgm.AddressesGetDefaultRequestType` — `shipping` = a shipment destination; `deposit` = where check deposits are sent.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Addresses.Get(ID) -> *usgm.AddressDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve one shipping or deposit address by its id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.AddressesGetRequest{
        ID: "id",
    }
client.Addresses.Get(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Addresses.Delete(ID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Permanently delete an address; this is destructive and cannot be undone
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.AddressesDeleteRequest{
        ID: "id",
    }
client.Addresses.Delete(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Addresses.Update(ID, request) -> *usgm.AddressDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update fields on an existing shipping or deposit address
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.UpdateAddressDto{
        ID: "id",
    }
client.Addresses.Update(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**type_:** `*usgm.UpdateAddressDtoType` — `shipping` = a shipment destination; `deposit` = where check deposits are sent.
    
</dd>
</dl>

<dl>
<dd>

**name:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**line1:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**line2:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**line3:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**city:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**state:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**postalCode:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**country:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**phoneNumber:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**taxID:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Addresses.Setdefault(ID) -> *usgm.AddressDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Make this address the default for its type, replacing the previous default
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.AddressesSetDefaultRequest{
        ID: "id",
    }
client.Addresses.Setdefault(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## bank-accounts
<details><summary><code>client.BankAccounts.BankAccountsList() -> *usgm.BankAccountPageDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List your bank accounts used for check deposits
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.BankAccountsListRequest{}
client.BankAccounts.BankAccountsList(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*int` — Page size, capped at 100.
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — Opaque page cursor — the `next_cursor` of the previous response. Omit for the first page.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.BankAccounts.BankAccountsCreate(request) -> *usgm.BankAccountDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Add a bank account for check deposits; account number is write-only
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.CreateBankAccountDto{
        BankName: "bank_name",
        BankState: "bank_state",
        AccountNumber: "account_number",
    }
client.BankAccounts.BankAccountsCreate(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**bankName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**bankState:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**accountNumber:** `string` — Full account number. Write-only — reads return `account_number_last4`.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.BankAccounts.BankAccountsGet(ID) -> *usgm.BankAccountDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve one bank account by id, returning only the last 4 digits
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.BankAccountsGetRequest{
        ID: "id",
    }
client.BankAccounts.BankAccountsGet(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.BankAccounts.BankAccountsDelete(ID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Permanently delete a bank account; this is destructive and cannot be undone
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.BankAccountsDeleteRequest{
        ID: "id",
    }
client.BankAccounts.BankAccountsDelete(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.BankAccounts.BankAccountsUpdate(ID, request) -> *usgm.BankAccountDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update the bank name, state, or account number on a bank account
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.UpdateBankAccountDto{
        ID: "id",
    }
client.BankAccounts.BankAccountsUpdate(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**bankName:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**bankState:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**accountNumber:** `*string` — Full account number. Write-only — reads return `account_number_last4`.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## account
<details><summary><code>client.Account.Get() -> *usgm.AccountDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Your account profile, including name, email, status, and PMB number
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Account.Get(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Account.Mailingaddress() -> *usgm.MailingAddressDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Your current USGM address, including PMB number
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Account.Mailingaddress(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## sandbox
<details><summary><code>client.Sandbox.Seed() -> *usgm.SeedResultDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Populate your sandbox mailbox with sample mail items for testing
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Sandbox.Seed(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Sandbox.Seedmail(request) -> *usgm.SeedMailResultDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Add one sample mail item to your sandbox mailbox, with optional overrides
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.SeedSandboxMailDto{}
client.Sandbox.Seedmail(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**senderName:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**mailType:** `*usgm.SeedSandboxMailDtoMailType` — Type of the seeded item. `LETTER` and `LARGELETTER` accept a `SCAN_REQUEST`; the rest accept an `UNBOXING_REQUEST`.
    
</dd>
</dl>

<dl>
<dd>

**weight:** `*float64` — Item weight, in pounds.
    
</dd>
</dl>

<dl>
<dd>

**measurement:** `*usgm.SeedSandboxMailDtoMeasurement` — Item dimensions, in inches.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Sandbox.Completescan(ID, request) -> *usgm.ScanDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Force a pending scan to completed in the sandbox for testing
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &usgm.CompleteSandboxScanDto{
        ID: "id",
    }
client.Sandbox.Completescan(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**label:** `*string` — Short document label the AI would produce, e.g. "Insurance". Set on the scan.
    
</dd>
</dl>

<dl>
<dd>

**summary:** `[]string` — Summary bullet points; retrievable via `GET /v1/scans/{id}/summary`.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

