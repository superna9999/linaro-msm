---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
<div>
<h2>SoC status</h2>
<p>This table contains full set of the features supported for each SoC.</p>
<table>
<thead>
{% include full_soc_header.liquid %}
</thead>
<tbody>
{% for d in site.soc %}
<tr>
<td><a href="{{d.url | absolute_url}}">{{d.name}}</a>
{%- if d.skus %}
	<span class="tooltip">(*)<span class="tooltiptext">
    {%- for sku in d.skus -%}
    {{sku}}{% unless forloop.last %}, {% endunless %}
    {%- endfor -%}
    </span></span>
{%- endif -%}
</td>
{% include full_soc_status.liquid %}
<td><a href="{{d.url | absolute_url}}">{{d.name}}</a>
{%- if d.skus %}
	<span class="tooltip">(*)<span class="tooltiptext">
    {%- for sku in d.skus -%}
    {{sku}}{% unless forloop.last %}, {% endunless %}
    {%- endfor -%}
    </span></span>
{%- endif -%}
</td>
</tr>
{% endfor %}
</tbody>
<tfoot>
{% include full_soc_header.liquid %}
</tfoot>
</table>
</div>

<div>
<h2>PMIC Status</h2>
<table>
<thead>
{% include full_pmic_header.liquid %}
</thead>
<tbody>
{% for d in site.pmic %}
<tr>
<td><a href="{{d.url | absolute_url}}">{{d.name}}</a></td>
{% include full_pmic_status.liquid %}
<td><a href="{{d.url | absolute_url}}">{{d.name}}</a></td>
</tr>
{% endfor %}
</tbody>
</table>
</div>
