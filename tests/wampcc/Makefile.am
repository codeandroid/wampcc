#
# Copyright (c) 2017 Darren Smith
#
# wampcc is free software; you can redistribute it and/or modify
# it under the terms of the MIT license. See LICENSE for details.
#

# Define compile & link flags for each target
AM_CPPFLAGS = -I$(top_srcdir)/include -I$(top_srcdir)/libs/wampcc $(libuvinc) -Wall -g3	\
-ggdb -std=c++11 -O0 -pthread -I$(top_srcdir)

AM_LDFLAGS=-L../../libs/wampcc -lwampcc $(LIBLS) -L$(jalsonlib) -lwampcc_json  $(libuvlib) -lcrypto -lpthread

check_PROGRAMS=test_basic_codecs test_connect_timeout test_tcp_socket_connect	\
test_evthread_wamp_session_destructor test_early_wamp_session_destructor		\
test_late_wamp_session_destructor test_tcp_socket_listen						\
test_tcp_socket_passive_disconnect test_wamp_session_fast_close test_tcp_socket	\
test_wamp_rpc test_misc test_router_functions test_send_and_close

# for make dist
EXTRA_DIST=test_common.h mini_test.h auth.py client_bad_logon_empty_realm.py	\
client_sends_bad_message.py basic_client.py										\
client_does_not_complete_handshake.py server_reject.py							\
client_abort_during_handshake.py client_immediate_disconnect.py wamplite.py


#test_late_dealer_destructor

# Dont use noinst_PROGRAMS here, otherwise the tests will always get build for
# each invocation of make
noinst_PROGRAMS=$(check_PROGRAMS)

TESTS=$(check_PROGRAMS)

test_misc_SOURCES=test_misc.cc

test_connect_timeout_SOURCES=test_connect_timeout.cc

test_late_wamp_session_destructor_SOURCES=test_late_wamp_session_destructor.cc

test_early_wamp_session_destructor_SOURCES=test_early_wamp_session_destructor.cc

test_evthread_wamp_session_destructor_SOURCES=test_evthread_wamp_session_destructor.cc

#test_late_dealer_destructor_SOURCES=test_late_dealer_destructor.cc

test_tcp_socket_connect_SOURCES=test_tcp_socket_connect.cc

test_tcp_socket_listen_SOURCES=test_tcp_socket_listen.cc

test_tcp_socket_passive_disconnect_SOURCES=test_tcp_socket_passive_disconnect.cc

test_wamp_session_fast_close_SOURCES=test_wamp_session_fast_close.cc

test_tcp_socket_SOURCES=test_tcp_socket.cc

test_wamp_rpc_SOURCES=test_wamp_rpc.cc

test_basic_codecs_SOURCES=test_basic_codecs.cc

test_router_functions_SOURCES=test_router_functions.cc

test_send_and_close_SOURCES=test_send_and_close.cc
