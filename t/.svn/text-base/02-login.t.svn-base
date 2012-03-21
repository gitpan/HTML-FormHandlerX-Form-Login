#!perl -T

use Test::More tests => 7;
use Test::Exception;

use HTML::FormHandlerX::Form::Login;

my $email = 'rob@intelcompute.com';
my $password = 'foo';

my $form;

lives_ok {
	$form = HTML::FormHandlerX::Form::Login->new( active => [ qw( email password ) ] );
} "Constructed ok and activated email and password";

lives_ok {
	$form->process( params => { email => $email, password => $password } );
} "Processed ok with email and password";

ok( $form->validated, "validated ok");
 


$email = '';

lives_ok {
	$form->process( params => { email => $email, password => $password } );
} "Processed ok with email and password";

ok( ! $form->validated, "email is required");



$email = 'rob@intelcompute.com';

$password = '';

lives_ok {
	$form->process( params => { email => $email, password => $password } );
} "Processed ok with email and password";

ok( ! $form->validated, "password is required");





 