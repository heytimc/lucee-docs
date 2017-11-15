<pre>
&lt;cffunction name="updateAddress" access="remote" output="false"&gt;
  &lt;cfargument name="addressId" type="number" required="yes"&gt;
  &lt;cfargument name="newAddress" type="string" required="yes"&gt;

  &lt;cftransaction isolation="read_committed"&gt;
    &lt;cfquery name="changeAddress" datasource="#application.config.DSN#"&gt;
  		update address set login_address = &lt;cfqueryparam value="#arguments.newAddress#" cfsqltype="CF_SQL_VARCHAR"&gt;
				where	id = &lt;cfqueryparam value="#arguments.addressId#" cfsqltype="CF_SQL_INTEGER"&gt;
    &lt;/cfquery&gt;
  &lt;/cftransaction&gt;
&lt;/cffunction&gt;
</pre>
