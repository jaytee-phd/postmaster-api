# Shipments

## Create a Shipment

### __POST__  /v1/shipments 

Creates a new shipment.

#### Request Parameters

<dt>to</dt>
<dd>The address where the shipment will go.
	<dl class="dl-horizontal">
		<dt>contact</dt>
		<dd>The contact name at the address. <i class="icon-star-empty"></i></dd>
		<dt>company</dt>
		<dd>The company name at the address. <i class="icon-star-empty"></i></dd>
		<dt>line1</dt>
		<dd>The first line of the street address.</dd>
		<dt>line2</dt>
		<dd>The second line of the street address (optional).</dd>
		<dt>line3</dt>
		<dd>The third line of the street address (optional).</dd>
		<dt>city</dt>
		<dd>The city.</dd>
		<dt>state</dt>
		<dd>The state (or province).</dd>
		<dt>zip_code</dt>
		<dd>The zip (or postal code).</dd>
		<dt>phone_no</dt>
		<dd>The phone number.</dd>
	</dl>
</dd>
<dt>from</dt>
<dd>The address where the shipment will come from. (optional, will use account default otherwise).</dd>
<dt>package</dt>
<dd>The specification of the package you are sending.
	<dl class="dl-horizontal">
		<dt>id <span class="dt_or">or</span> name</dt>
		<dd>Id or name of user-defined package (optional, see <a href="#createbox">Create Box</a>)</dd>
		<dt>type</dt>
		<dd>The type of package (letter, tube, etc. see <a href="#packages">packages</a>)</dd>
		<dt>width</dt>
		<dd>Package width (integer). <i class="icon-star"></i></dd>
		<dt>length</dt>
		<dd>Package length (integer). <i class="icon-star"></i></dd>
		<dt>height</dt>
		<dd>Package height (integer). <i class="icon-star"></i></dd>
		<dt>weight</dt>
		<dd>Package weight (float).</dd>
		<dt>weight_units</dt>
		<dd>The units of weight: LB, OZ, KG, G (optional, default: LB).</dd>
		<dt>dimension_units</dt>
		<dd>The units of size: IN, FT, CM, M (optional, default: IN).</dd>
		<dt>declared_value</dt>
		<dd>Package declared value (insured value), in US dollars (optional, float).</dd>
		<dt>customs</dt>
		<dd>Customs information for international shipments (see <a href="#international">International</a>).
	</dl>
</dd>
<dt>carrier</dt>
<dd>The specific carrier you would like to use (optional, leave blank for lowest cost).</dd>
<dt>service</dt>
<dd>The service level you would like for this package (optional; see <a href="#services">Service levels</a> for more information).</dd>
<dt>po_number</dt>
<dd>Purchase order number (optional).</dd>
<dt>references</dt>
<dd>Additional references to other orders (list, optional).</dd>
<dt>options</dt>
<dd>Carrier-specific options (dictionary, optional - see below).</dd>
<dt>signature</dt>
<dd>Type of signature required (optional, options: NONE, GENERAL or ADULT - default: NONE).</dd>
<dt>label</dt>
<dd>The label specific options (optional). See <a href="#label-formats">Label formats</a> and <a href="#label-sizes">Label sizes</a>.
	<dl class="dl-horizontal">
		<dt>type</dt>
		<dd>The type of printer you are using (optional, default: NORMAL).</dd>
		<dt>format</dt>
		<dd>The file format of returned label (optional, default: PNG).</dd>
		<dt>size</dt>
		<dd>The size of label you wish to print (optional, default: SMALL).</dd>
	</dl>
</dd>

## List Shipments

List shipments that were created trough Postmaster.

### __GET__ /v1/shipments

#### Request Parameters

 * _limit_ - The number of shipments to get (optional, default: 10).
 * _cursor_ - The cursor offset (optional).
 * _status_ - Extract shipments only with provided status (optional).

#### Available statuses:

__Processing, In-Transit, Out For Delivery, Delivered, Voided, Exception, Returned.__

## Cancel Shipment
### __POST__ /v1/shipments/_ID_/void

Void a shipment. Shipments can only be voided before being picked up by the carrier.
A voided shipment will still be visible in the development dashboard.
    
#### Request Parameters
 * _ID_ - Shipment ID specified in URL ([0-9]+).

