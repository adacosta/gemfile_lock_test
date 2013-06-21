gemfile_lock_test
=================

Test gemfile lock dependency specifications

## Description ##
This is a test to demonstrate how dependencies specified in the Gemfile.lock retain their specification version.

### Pre-test Verification ###
1. In Gemfile.lock, under webmock, note ```crack (>= 0.1.7)``` is specified.
2. In Gemfile.lock, note ```crack (0.3.2)``` is specified.
3. Run ```gem search crack -ra | grep "^crack ("```
4. Verify a version newer than crack 0.3.2 is specified (e.g. 0.4.0)

### Test Steps ###
1. Run ```bundle install --deployment```

### Post-test Verification ###

1. Verify ```Installing crack (0.3.2)``` is output to stdout.
2. Run ```find ./ -type d -name crack-0.3.2```
3. Verify crack 0.3.2 was installed in the vendor path.
