# infusionsoft-order-id

add_filter('woocommerce_order_number', 'ov_iw_woocommerce_order_number',10,2);

function ov_iw_woocommerce_order_number($last_id, $wcorder) {
  $wcid = $wcorder->id;
  $infusion_order_id = get_post_meta( $wcid, 'infusionsoft_order_id', true );
  if($infusion_order_id) return $infusion_order_id;
  else return $last_id;
}
