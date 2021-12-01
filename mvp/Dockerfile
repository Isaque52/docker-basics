# We don't want to inherit from any dockerfile previously
# As such we comment out the FROM syntax
# FROM scratch
# We want to copy a file. This syntax allows us to copy a file from our host pc to our destination docker image
# We are specifying it in the same way as bash would be specified
# So it is specified as COPY {host-file} {destination}
COPY hello.sh /
# This runs the command specified. You pass in the command as an array, with each argument as a portion of the command
# to be executed. You can also pass in the command as a direct full string which we will do below
CMD ["./hello.sh"]
# Execute the command again but using direct string representation
CMD "./hello.sh"
