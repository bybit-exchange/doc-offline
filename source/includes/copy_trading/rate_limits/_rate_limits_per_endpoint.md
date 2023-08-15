
### t(:perendpoint)
<table class="custom_table">
  <tr>
    <th>t(:row_comment_rate_limit)</th>
    <th>t(:row_comment_path)</th>
    <th>t(:row_comment_consume)</th>
  </tr>
  <tr>
    <td rowspan="4">75/min</td>  
  </tr>
  <tr><td>/contract/v3/private/copytrading/position/set-leverage </td><td>1 / request</td></tr>
  <tr><td>/contract/v3/private/copytrading/position/close  </td><td>1 / request</td></tr>
  <tr><td>/contract/v3/private/copytrading/position/list  </td><td>1 / request</td></tr>
<tr>
    <td rowspan="5">100/min</td>  
  </tr>
 <tr><td>/contract/v3/private/copytrading/order/create </td><td>1 / request</td></tr>
  <tr><td>/contract/v3/private/copytrading/order/close </td><td>1 / request</td></tr>
  <tr><td>/contract/v3/private/copytrading/order/cancel  </td><td>1 / request</td></tr>
  <tr><td>/contract/v3/private/copytrading/order/list  </td><td>1 / request</td></tr>

  <tr>
    <td rowspan="3">120/min</td>
  </tr>
  <tr><td>/contract/v3/private/copytrading/wallet/balance</td><td>1 / request</td></tr>
  <tr><td>/contract/v3/private/copytrading/wallet/transfer</td><td>1 / request</td></tr>
</table>
