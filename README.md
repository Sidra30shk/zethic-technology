Task 1:

Backend:

class Insect {
  constructor(x, y, heading) {
    this.x = x;
    this.y = y;
    this.heading = heading;
  }

  turnLeft() {
    switch (this.heading) {
      case "N":
        this.heading = "W";
        break;
      case "W":
        this.heading = "S";
        break;
      case "S":
        this.heading = "E";
        break;
      case "E":
        this.heading = "N";
        break;
      default:
        break;
    }
  }

  turnRight() {
    switch (this.heading) {
      case "N":
        this.heading = "E";
        break;
      case "E":
        this.heading = "S";
        break;
      case "S":
        this.heading = "W";
        break;
      case "W":
        this.heading = "N";
        break;
      default:
        break;
    }
  }

  moveForward() {
    switch (this.heading) {
      case "N":
        this.y += 1;
        break;
      case "E":
        this.x += 1;
        break;
      case "S":
        this.y -= 1;
        break;
      case "W":
        this.x -= 1;
        break;
      default:
        break;
    }
  }

  navigate(commands) {
    for (let i = 0; i < commands.length; i++) {
      switch (commands[i]) {
        case "L":
          this.turnLeft();
          break;
        case "R":
          this.turnRight();
          break;
        case "F":
          this.moveForward();
          break;
        default:
          break;
      }
    }
  }
}

module.exports = Insect;

Frontend:

import React, { useState } from "react";
import { useDispatch } from "react-redux";
import { navigateInsect } from "./actions";

const NavigateForm = () => {
  const [x, setX] = useState(0);
  const [y, setY] = useState(0);
  const [heading, setHeading] = useState("N");
  const [commands, setCommands] = useState("");
  const dispatch = useDispatch();

  const handleSubmit = (e) => {
    e.preventDefault();
    dispatch(navigateInsect(x, y, heading, commands.split("")));
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>
        X:
        <input type="number" value={x} onChange={(e) => setX(e.target.value)} />
      </label>
      <label>
        Y:
        <input type="number" value={y} onChange={(e) => setY(e.target.value)} /


Task 2:

 <!DOCTYPE html>
<html lang="en">
	<head>
		<!-- Meta -->
		<meta charset="utf-8">
		<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
		<meta name="description" content="">
		<meta name="author" content="">
	    <meta name="keywords" content="MediaCenter, Template, eCommerce">
	    <meta name="robots" content="all">

	    <title>My Cart</title>
	    <link rel="stylesheet" href="assets/css/bootstrap.min.css">
	    <link rel="stylesheet" href="assets/css/main.css">
	    <link rel="stylesheet" href="assets/css/green.css">
	    <link rel="stylesheet" href="assets/css/owl.carousel.css">
		<link rel="stylesheet" href="assets/css/owl.transitions.css">
		<!--<link rel="stylesheet" href="assets/css/owl.theme.css">-->
		<link href="assets/css/lightbox.css" rel="stylesheet">
		<link rel="stylesheet" href="assets/css/animate.min.css">
		<link rel="stylesheet" href="assets/css/rateit.css">
		<link rel="stylesheet" href="assets/css/bootstrap-select.min.css">

		<!-- Demo Purpose Only. Should be removed in production -->
		<link rel="stylesheet" href="assets/css/config.css">

		<link href="assets/css/green.css" rel="alternate stylesheet" title="Green color">
		<link href="assets/css/blue.css" rel="alternate stylesheet" title="Blue color">
		<link href="assets/css/red.css" rel="alternate stylesheet" title="Red color">
		<link href="assets/css/orange.css" rel="alternate stylesheet" title="Orange color">
		<link href="assets/css/dark-green.css" rel="alternate stylesheet" title="Darkgreen color">
		<!-- Demo Purpose Only. Should be removed in production : END -->

		
		<!-- Icons/Glyphs -->
		<link rel="stylesheet" href="assets/css/font-awesome.min.css">

        <!-- Fonts --> 
		<link href='http://fonts.googleapis.com/css?family=Roboto:300,400,500,700' rel='stylesheet' type='text/css'>
		
		<!-- Favicon -->
		<link rel="shortcut icon" href="assets/images/favicon.ico">

		<!-- HTML5 elements and media queries Support for IE8 : HTML5 shim and Respond.js -->
		<!--[if lt IE 9]>
			<script src="assets/js/html5shiv.js"></script>
			<script src="assets/js/respond.min.js"></script>
		<![endif]-->

	</head>
    <body class="cnt-home">
	
		
	
		<!-- ============================================== HEADER ============================================== -->
<header class="header-style-1">

<div class="top-bar animate-dropdown">
	<div class="container">
		<div class="header-top-inner">
			<div class="cnt-account">
				<ul class="list-unstyled">


					<li><a href="my-account.php"><i class="icon fa fa-user"></i>My Account</a></li>
					<li><a href="my-wishlist.php"><i class="icon fa fa-heart"></i>Wishlist</a></li>
					<li><a href="my-cart.php"><i class="icon fa fa-shopping-cart"></i>My Cart</a></li>
					<li><a href="login.php"><i class="icon fa fa-sign-in"></i>Login</a></li>
	
				</ul>
			</div><!-- /.cnt-account -->

<div class="cnt-block">
				<ul class="list-unstyled list-inline">
					<li class="dropdown dropdown-small">
						<a href="track-orders.php" class="dropdown-toggle" ><span class="key">Track Order</b></a>
						
					</li>

				
				</ul>
			</div>
			
			<div class="clearfix"></div>
		</div><!-- /.header-top-inner -->
	</div><!-- /.container -->
</div><!-- /.header-top -->	<div class="main-header">
		<div class="container">
			<div class="row">
				<div class="col-xs-12 col-sm-12 col-md-3 logo-holder">
					<!-- ============================================================= LOGO ============================================================= -->
<div class="logo">
	<a href="index.php">
		
		<h2>Shopping Portal</h2>

	</a>
</div>		
</div>
<div class="col-xs-12 col-sm-12 col-md-6 top-search-holder">
<div class="search-area">
<form name="search" method="post" action="search-result.php">
        <div class="control-group">

            <input class="search-field" placeholder="Search here..." name="product" required="required" />

            <button class="search-button" type="submit" name="search"></button>    

        </div>
    </form>
</div><!-- /.search-area -->
<!-- ============================================================= SEARCH AREA : END ============================================================= -->				</div><!-- /.top-search-holder -->

				<div class="col-xs-12 col-sm-12 col-md-3 animate-dropdown top-cart-row">
					<!-- ============================================================= SHOPPING CART DROPDOWN ============================================================= -->
	<div class="dropdown dropdown-cart">
		<a href="#" class="dropdown-toggle lnk-cart" data-toggle="dropdown">
			<div class="items-cart-inner">
				<div class="total-price-basket">
					<span class="lbl">cart -</span>
					<span class="total-price">
						<span class="sign">Rs.</span>
						<span class="value">147960.00</span>
					</span>
				</div>
				<div class="basket">
					<i class="glyphicon glyphicon-shopping-cart"></i>
				</div>
				<div class="basket-item-count"><span class="count">4</span></div>
			
		    </div>
		</a>
		<ul class="dropdown-menu">
		
		 		
		
			<li>
				<div class="cart-item product-summary">
					<div class="row">
						<div class="col-xs-4">
							<div class="image">
								<a href="product-details.php?pid=2"><img  src="admin/productimages/2/apple-iphone-6-1.jpeg" width="35" height="50" alt=""></a>
							</div>
						</div>
						<div class="col-xs-7">
							
							<h3 class="name"><a href="product-details.php?pid=2">Apple iPhone 6 (Silver, 16 GB)</a></h3>
							<div class="price">Rs.36990*4</div>
						</div>
						
					</div>
				</div><!-- /.cart-item -->
			
								<div class="clearfix"></div>
			<hr>
		
			<div class="clearfix cart-total">
				<div class="pull-right">
					
						<span class="text">Total :</span><span class='price'>Rs.147960.00</span>
						
				</div>
			
				<div class="clearfix"></div>
					
				<a href="my-cart.php" class="btn btn-upper btn-primary btn-block m-t-20">My Cart</a>	
			</div><!-- /.cart-total-->
					
				
		</li>
		</ul><!-- /.dropdown-menu-->
	</div><!-- /.dropdown-cart -->




<!-- ============================================================= SHOPPING CART DROPDOWN : END============================================================= -->				</div><!-- /.top-cart-row -->
			</div><!-- /.row -->

		</div><!-- /.container -->

	</div><div class="header-nav animate-dropdown">
    <div class="container">
        <div class="yamm navbar navbar-default" role="navigation">
            <div class="navbar-header">
                <button data-target="#mc-horizontal-menu-collapse" data-toggle="collapse" class="navbar-toggle collapsed" type="button">
                    <span class="sr-only">Toggle navigation</span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                </button>
            </div>
            <div class="nav-bg-class">
                <div class="navbar-collapse collapse" id="mc-horizontal-menu-collapse">
	<div class="nav-outer">
		<ul class="nav navbar-nav">
			<li class="active dropdown yamm-fw">
				<a href="index.php" data-hover="dropdown" class="dropdown-toggle">Home</a>
				
			</li>
              
			<li class="dropdown yamm">
				<a href="category.php?cid=3"> Books</a>
			
			</li>
			
			<li class="dropdown yamm">
				<a href="category.php?cid=4"> Electronics</a>
			
			</li>
			
			<li class="dropdown yamm">
				<a href="category.php?cid=5"> Furniture</a>
			
			</li>
			
			<li class="dropdown yamm">
				<a href="category.php?cid=6"> Fashion</a>
			
			</li>
			
			
		</ul><!-- /.navbar-nav -->
		<div class="clearfix"></div>				
	</div>
</div>


            </div>
        </div>
    </div>
</div></header>
<!-- ============================================== HEADER : END ============================================== -->
<div class="breadcrumb">
	<div class="container">
		<div class="breadcrumb-inner">
			<ul class="list-inline list-unstyled">
				<li><a href="#">Home</a></li>
				<li class='active'>Shopping Cart</li>
			</ul>
		</div><!-- /.breadcrumb-inner -->
	</div><!-- /.container -->
</div><!-- /.breadcrumb -->

<div class="body-content outer-top-xs">
	<div class="container">
		<div class="row inner-bottom-sm">
			<div class="shopping-cart">
				<div class="col-md-12 col-sm-12 shopping-cart-table ">
	<div class="table-responsive">
<form name="cart" method="post">	
		<table class="table table-bordered">
			<thead>
				<tr>
					<th class="cart-romove item">Remove</th>
					<th class="cart-description item">Image</th>
					<th class="cart-product-name item">Product Name</th>
			
					<th class="cart-qty item">Quantity</th>
					<th class="cart-sub-total item">Price Per unit</th>
					<th class="cart-sub-total item">Shipping Charge</th>
					<th class="cart-total last-item">Grandtotal</th>
				</tr>
			</thead><!-- /thead -->
			<tfoot>
				<tr>
					<td colspan="7">
						<div class="shopping-cart-btn">
							<span class="">
								<a href="index.php" class="btn btn-upper btn-primary outer-left-xs">Continue Shopping</a>
								<input type="submit" name="submit" value="Update shopping cart" class="btn btn-upper btn-primary pull-right outer-right-xs">
							</span>
						</div><!-- /.shopping-cart-btn -->
					</td>
				</tr>
			</tfoot>
			<tbody>
 
				<tr>
					<td class="romove-item"><input type="checkbox" name="remove_code[]" value="2" /></td>
					<td class="cart-image">
						<a class="entry-thumbnail" href="detail.html">
						    <img src="admin/productimages/2/apple-iphone-6-1.jpeg" alt="" width="114" height="146">
						</a>
					</td>
					<td class="cart-product-name-info">
						<h4 class='cart-product-description'><a href="product-details.php?pid=2" >Apple iPhone 6 (Silver, 16 GB)</a></h4>
						<div class="row">
							<div class="col-sm-4">
								<div class="rating rateit-small"></div>
							</div>
							<div class="col-sm-8">
								<div class="reviews">
									( 0 Reviews )
								</div>
															</div>
						</div><!-- /.row -->
						
					</td>
					<td class="cart-product-quantity">
						<div class="quant-input">
				                <div class="arrows">
				                  <div class="arrow plus gradient"><span class="ir"><i class="icon fa fa-sort-asc"></i></span></div>
				                  <div class="arrow minus gradient"><span class="ir"><i class="icon fa fa-sort-desc"></i></span></div>
				                </div>
				             <input type="text" value="4" name="quantity[2]">
				             
			              </div>
		            </td>
					<td class="cart-product-sub-total"><span class="cart-sub-total-price">Rs 36990.00</span></td>
<td class="cart-product-sub-total"><span class="cart-sub-total-price">Rs 0.00</span></td>

					<td class="cart-product-grand-total"><span class="cart-grand-total-price">147960.00</span></td>
				</tr>

								
			</tbody><!-- /tbody -->
		</table><!-- /table -->
		
	</div>
</div><!-- /.shopping-cart-table -->			<div class="col-md-4 col-sm-12 estimate-ship-tax">
	<table class="table table-bordered">
		<thead>
			<tr>
				<th>
					<span class="estimate-title">Shipping Address</span>
				</th>
			</tr>
		</thead>
		<tbody>
				<tr>
					<td>
						<div class="form-group">
		
						</div>
					
					</td>
				</tr>
		</tbody><!-- /tbody -->
	</table><!-- /table -->
</div>

<div class="col-md-4 col-sm-12 estimate-ship-tax">
	<table class="table table-bordered">
		<thead>
			<tr>
				<th>
					<span class="estimate-title">Billing Address</span>
				</th>
			</tr>
		</thead>
		<tbody>
				<tr>
					<td>
						<div class="form-group">
		
		
						</div>
					
					</td>
				</tr>
		</tbody><!-- /tbody -->
	</table><!-- /table -->
</div>
<div class="col-md-4 col-sm-12 cart-shopping-total">
	<table class="table table-bordered">
		<thead>
			<tr>
				<th>
					
					<div class="cart-grand-total">
						Grand Total<span class="inner-left-md">147960.00</span>
					</div>
				</th>
			</tr>
		</thead><!-- /thead -->
		<tbody>
				<tr>
					<td>
						<div class="cart-checkout-btn pull-right">
							<button type="submit" name="ordersubmit" class="btn btn-primary">PROCCED TO CHEKOUT</button>
						
						</div>
					</td>
				</tr>
		</tbody><!-- /tbody -->
	</table>
	</div>			</div>
		</div> 
		</form>
<div id="brands-carousel" class="logo-slider wow fadeInUp">
		<h3 class="section-title">Our Brands</h3>
		<div class="logo-slider-inner">	
			<div id="brand-slider" class="owl-carousel brand-slider custom-carousel owl-theme">
				<div class="item">
					<a href="#" class="image">
						<img data-echo="brandsimage/aoc.jpg" src="assets/images/blank.gif" alt="">
					</a>	
				</div><!--/.item-->

				<div class="item">
					<a href="#" class="image">
						<img data-echo="brandsimage/bajaj.jpg" src="assets/images/blank.gif" alt="">
					</a>	
				</div><!--/.item-->

				<div class="item">
					<a href="#" class="image">
						<img data-echo="brandsimage/blackberry.jpg" src="assets/images/blank.gif" alt="">
					</a>	
				</div><!--/.item-->

				<div class="item">
					<a href="#" class="image">
						<img data-echo="brandsimage/canon.jpg" src="assets/images/blank.gif" alt="">
					</a>	
				</div>

				<div class="item">
					<a href="#" class="image">
						<img data-echo="brandsimage/compas.jpg" src="assets/images/blank.gif" alt="">
					</a>	
				</div>

				<div class="item">
					<a href="#" class="image">
						<img data-echo="brandsimage/daikin.jpg" src="assets/images/blank.gif" alt="">
					</a>	
				</div>

				<div class="item">
					<a href="#" class="image">
						<img data-echo="brandsimage/dell.jpg" src="assets/images/blank.gif" alt="">
					</a>	
				</div>
<div class="item">
					<a href="#" class="image">
						<img data-echo="brandsimage/samsung.jpg" src="assets/images/blank.gif" alt="">
					</a>	
				</div>
				<div class="item">
					<a href="#" class="image">
						<img data-echo="brandsimage/hcl.jpg" src="assets/images/blank.gif" alt="">
					</a>	
				</div>

				

				<div class="item">
					<a href="#" class="image">
						<img data-echo="brandsimage/sony.jpg" src="assets/images/blank.gif" alt="">
					</a>	
				</div>

				<div class="item">
					<a href="#" class="image">
						<img data-echo="brandsimage/voltas.jpg" src="assets/images/blank.gif" alt="">
					</a>	
				</div>

				<div class="item">
					<a href="#" class="image">
						<img data-echo="brandsimage/lg.jpg" src="assets/images/blank.gif" alt="">
					</a>	
				</div>

				<div class="item">
					<a href="#" class="image">
						<img data-echo="brandsimage/lenovo.jpg" src="assets/images/blank.gif" alt="">
					</a>	
				</div>




		    </div><!-- /.owl-carousel #logo-slider -->
		</div><!-- /.logo-slider-inner -->
	
</div><!-- /.logo-slider -->1</div>
</div>
<footer id="footer" class="footer color-bg">
	  <div class="links-social inner-top-sm">
        <div class="container">
            <div class="row">
            	<div class="col-xs-12 col-sm-6 col-md-4">
            		 <!-- ============================================================= CONTACT INFO ============================================================= -->
<div class="contact-info">
    <div class="footer-logo">
        <div class="logo">
            <a href="index.php">
                
<h3>Shopping Portal</h3>
            </a>
        </div><!-- /.logo -->
    
    </div><!-- /.footer-logo -->

     <div class="module-body m-t-20">
        <p class="about-us"> Nam libero tempore, cum soluta nobis est ses  eligendi optio cumque cum soluta nobis est ses  eligendi optio cumque.</p>
    
        <div class="social-icons">
            
        <a href="http://facebook.com/transvelo" class='active'><i class="icon fa fa-facebook"></i></a>
        <a href="#"><i class="icon fa fa-twitter"></i></a>
        <a href="#"><i class="icon fa fa-linkedin"></i></a>
        <a href="#"><i class="icon fa fa-rss"></i></a>
        <a href="#"><i class="icon fa fa-pinterest"></i></a>

        </div><!-- /.social-icons -->
    </div><!-- /.module-body -->

</div><!-- /.contact-info -->
<!-- ============================================================= CONTACT INFO : END ============================================================= -->            	</div><!-- /.col -->

            	<div class="col-xs-12 col-sm-6 col-md-4">
            		 <!-- ============================================================= CONTACT TIMING============================================================= -->
<div class="contact-timing">
	<div class="module-heading">
		<h4 class="module-title">opening time</h4>
	</div><!-- /.module-heading -->

	<div class="module-body outer-top-xs">
		<div class="table-responsive">
			<table class="table">
				<tbody>
					<tr><td>Monday-Friday:</td><td class="pull-right">08.00 To 18.00</td></tr>
					<tr><td>Saturday:</td><td class="pull-right">09.00 To 20.00</td></tr>
					<tr><td>Sunday:</td><td class="pull-right">10.00 To 20.00</td></tr>
				</tbody>
			</table>
		</div><!-- /.table-responsive -->
	</div><!-- /.module-body -->
</div><!-- /.contact-timing -->
<!-- ============================================================= CONTACT TIMING : END ============================================================= -->            	</div><!-- /.col -->

            	<div class="col-xs-12 col-sm-6 col-md-4">
            		 <!-- ============================================================= INFORMATION============================================================= -->
<div class="contact-information">
	<div class="module-heading">
		<h4 class="module-title">information</h4>
	</div><!-- /.module-heading -->

	<div class="module-body outer-top-xs">
        <ul class="toggle-footer" style="">
            <li class="media">
                <div class="pull-left">
                     <span class="icon fa-stack fa-lg">
                      <i class="fa fa-circle fa-stack-2x"></i>
                      <i class="fa fa-map-marker fa-stack-1x fa-inverse"></i>
                    </span>
                </div>
                <div class="media-body">
                    <p>Surigao City, Philippines</p>
                </div>
            </li>

              <li class="media">
                <div class="pull-left">
                     <span class="icon fa-stack fa-lg">
                      <i class="fa fa-circle fa-stack-2x"></i>
                      <i class="fa fa-mobile fa-stack-1x fa-inverse"></i>
                    </span>
                </div>
                <div class="media-body">
                    <p>(011) 000000000000<br>(011) 000000000000</p>
                </div>
            </li>

              <li class="media">
                <div class="pull-left">
                     <span class="icon fa-stack fa-lg">
                      <i class="fa fa-circle fa-stack-2x"></i>
                      <i class="fa fa-envelope fa-stack-1x fa-inverse"></i>
                    </span>
                </div>
                <div class="media-body">
                    <span><a href="https://www.campcodes.com/">www.campcodes.com</a></span>
                </div>
            </li>
              
            </ul>
    </div><!-- /.module-body -->
</div><!-- /.contact-timing -->
<!-- ============================================================= INFORMATION : END ============================================================= -->            	</div><!-- /.col -->
            </div><!-- /.row -->
        </div><!-- /.container -->
    </div><!-- /.links-social -->

    
	<script src="assets/js/jquery-1.11.1.min.js"></script>
	
	<script src="assets/js/bootstrap.min.js"></script>
	
	<script src="assets/js/bootstrap-hover-dropdown.min.js"></script>
	<script src="assets/js/owl.carousel.min.js"></script>
	
	<script src="assets/js/echo.min.js"></script>
	<script src="assets/js/jquery.easing-1.3.min.js"></script>
	<script src="assets/js/bootstrap-slider.min.js"></script>
    <script src="assets/js/jquery.rateit.min.js"></script>
    <script type="text/javascript" src="assets/js/lightbox.min.js"></script>
    <script src="assets/js/bootstrap-select.min.js"></script>
    <script src="assets/js/wow.min.js"></script>
	<script src="assets/js/scripts.js"></script>

	<!-- For demo purposes – can be removed on production -->
	
	<script src="switchstylesheet/switchstylesheet.js"></script>
	
	<script>
		$(document).ready(function(){ 
			$(".changecolor").switchstylesheet( { seperator:"color"} );
			$('.show-theme-options').click(function(){
				$(this).parent().toggleClass('open');
				return false;
			});
		});

		$(window).bind("load", function() {
		   $('.show-theme-options').delay(2000).trigger('click');
		});
	</script>
	<!-- For demo purposes – can be removed on production : End -->
</body>
</html>

i.	With the help of xampp we can view this application.
ii.	http://localhost/onlineshoppingportal/Onlineshoppingportal/shopping/index.php
iii.	Once you click on this link you’ll be redirected to the application.
iv.	The application contains the below mentioned pages:
•	Login Page
•	Home Page
•	Cart list Page
    
 
 
