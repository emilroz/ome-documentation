OMERO.fs
========

**OMERO.fs** is a series of on-going changes designed to improve the way an 
OMERO.server interacts with existing directories of acquired image data. It 
currently consists of two components:

**OMERO.dropbox** is designed for watching a
directory and kicking off an automatic import. The configuration of the
DropBox system is covered on the :doc:`/sysadmins/dropbox` system 
administrator's page.

**OMERO.fs Managed Repository** is designed to store original data in an
unaltered form without requiring the data duplication that was carried
out by a pre-5.0 import. The changes to the import system mean that an
OMERO.fs server stores the original files in the ``ManagedRepository``,
preserving file names and any nested directory structure. The repository
may even contain direct :doc:`in-place links
</sysadmins/in-place-import>` to original data without an file upload
step. These changes improve the way OMERO deals with High Content
Screening (HCS) and other complex heterogeneous data types, reducing
storage requirements and using Bio-Formats to recognize :ref:`filesets`
(groups of files which correspond to multi-dimensional images and
accompanying information) so they can be treated as single entities
within the OMERO clients. OMERO.fs has some :ref:`configuration
properties <fs_configuration>` that allow sysadmins to customize it for
their site; developers should be aware of the :doc:`how the new import
process works </developers/ImportFS>` and how this is affected by the
configuration.
