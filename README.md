# SpaceWizards.NetSerializer - A fast, simple serializer for .Net

SpaceWizards.NetSerializer is the Space Wizards fork of
[NetSerializer](https://github.com/tomba/netserializer) by Tomi Valkeinen.

NetSerializer is a simple and very fast serializer for .Net languages, aimed at
sending data over the network.

The main pros of NetSerializer are:

- Excellent for network serialization
- Supports classes, structs, enums, interfaces, abstract classes
- No versioning or other extra information is serialized, only what is strictly needed
- No type IDs for primitive types, structs or sealed classes, so less data to be sent
- No dynamic type lookup for primitive types, structs or sealed classes, so
  deserialization is faster
- No extra attributes needed (like DataContract/Member), just add the standard
  [Serializable]
- Thread safe without locks
- The data is written to the stream and read from the stream directly, without
  the need for temporary buffers

The simpleness of NetSerializer has a drawback which must be considered by the
user: no versioning or other meta information is sent, which means that the
sender and the receiver have to have the same versions of the types being
serialized.

This means that it's a bad idea to save the serialized data for longer periods
of time, as a version upgrade could make the data non-deserializable.

For this reason the best (and perhaps only) use for NetSerializer is
for sending data over network, between a client and a server which have
verified version compatibility when the connection is made.

## Documentation

See [Documentation](Doc.md) page.

## Performance

See [Performance](Performance.md) page.

## License

MPL-2.0, see [LICENSE](LICENSE). Original work copyright Tomi Valkeinen.
